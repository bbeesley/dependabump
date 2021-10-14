# dependabump

A simple action to update dependencies on an npm project. Works with single npm modules in a repo as well as lerna projects containing multiple modules.

## Details

This is a single workflow step to perform the following tasks without lots of boilerplate in your github actions workflow files.

* NPM Auth - (Optional) Authenticate with a private npm registry before trying to install dependencies
* NPM Install - Install dependencies using npm ci, and if a lerna config file is present, run lerna bootstrap in ci mode.
* Package Update - Checks for updates to your dependencies using the `npm-check-updates` cli module. Runs against base package json as well as lerna package json files if present. Cleans modules and lockfiles and re creates them using the new bumped versions.
* Create PR - Commits the updated package.json and package-lock.json files to a new branch (`dependencies` by default), force pushes the branch, and creates a pull request against the main branch.

## Options

| name                       | description                                       | required | default                              |
|----------------------------|---------------------------------------------------|----------|--------------------------------------|
|  private-npm-token         | API token for a private npm repository            | false    |                                      |
|  private-npm-domain        | URL for a private npm repository                  | false    |                                      |
|  filter                     | Scope to limit dependency updates by              | false    | ''                                   |
|  reject                    | Scope to reject dependency updates by             | false    | ''                                   |
|  commit-message            | Commit message for dependabump commits            | true     | 'chore(deps): bump all dependencies' |
|  base-branch               | Base branch for pull requests                     | true     | 'main'                               |
|  dependabump-branch        | Branch to push dependency updates to              | true     | 'dependencies'                       |
|  dependabump-major-branch  | Branch to push major dependency updates to        | true     | 'major-dependencies'                 |
|  commit-author             | github username for commit author                 | true     | 'dependabump'                        |
|  working-dir               | optional path to your npm package.json            | false    |                                      |

## Required Environment Variables

* GITHUB_TOKEN - used to authenticate with github when pushing and creating PRs
  
## Example Workflow

```yaml
name: dependabump
on: repository_dispatch
jobs:
  update:
    runs-on: ubuntu-latest
    timeout-minutes: 20
    steps:
      - uses: actions/checkout@v2 # clone the repo
        with:
          token: ${{ secrets.GITHUB_PERSONAL_ACCESS_TOKEN }} # if you need special access to push commits
      - uses: actions/setup-node@v2 # ensure nodejs is installed at whatever version you use
        with:
          node-version: '14.17'
      - uses: bbeesley/dependabump@main
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }} # token to use when creating PRs 
        with:
          private-npm-token: ${{ secrets.ARTIFACTORY_TOKEN }} # npm token to access private registry (if used)
          private-npm-domain: npm.beesley.dev # domain name for private npm registry (if used)
          filter: '@bbeesley/*' # scope to limit module updates by, possible updates are matched against this pattern
          base-branch: master # target branch to create PRs against
          dependabump-branch: dependabump # branch to push dependency updates to
          dependabump-major-branch: major-deps # branch to push major dependency updates to
          commit-author: my-github-bot # github user to associate commits to
          commit-message: 'chore(deps): update ALL the things!' # commit message to use for dependency update commits
          working-dir: code/package # path to the directory your package.json is in, if not in repo root
```

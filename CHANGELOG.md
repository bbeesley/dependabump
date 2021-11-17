## [1.4.20](https://github.com/atlantis-devs/dependabump/compare/v1.4.19...v1.4.20) (2021-11-17)

## [1.4.19](https://github.com/atlantis-devs/dependabump/compare/v1.4.18...v1.4.19) (2021-11-17)

## [1.4.18](https://github.com/atlantis-devs/dependabump/compare/v1.4.17...v1.4.18) (2021-11-09)


### Reverts

* Revert "fix: pin npx npm-check-updates to v11.8.5 to avoid breaking change until fix" ([97d1d86](https://github.com/atlantis-devs/dependabump/commit/97d1d8619ff30f8f6518524930b16d329dee7ead))

## [1.4.17](https://github.com/atlantis-devs/dependabump/compare/v1.4.16...v1.4.17) (2021-11-09)


### Bug Fixes

* pin npx npm-check-updates to v11.8.5 to avoid breaking change until fix ([dd5c1c9](https://github.com/atlantis-devs/dependabump/commit/dd5c1c9f5b501107ebc02c2fe0141438501497fd))

## [1.4.16](https://github.com/atlantis-devs/dependabump/compare/v1.4.15...v1.4.16) (2021-11-01)

## [1.4.15](https://github.com/atlantis-devs/dependabump/compare/v1.4.14...v1.4.15) (2021-11-01)

## [1.4.14](https://github.com/atlantis-devs/dependabump/compare/v1.4.13...v1.4.14) (2021-11-01)

## [1.4.13](https://github.com/atlantis-devs/dependabump/compare/v1.4.12...v1.4.13) (2021-11-01)

## [1.4.12](https://github.com/atlantis-devs/dependabump/compare/v1.4.11...v1.4.12) (2021-10-25)


### Bug Fixes

* do include quotes in filter strings, but only for the lerna commands ([13b5989](https://github.com/atlantis-devs/dependabump/commit/13b5989714a848fc8b9f6026c7365f1b18240221))

## [1.4.11](https://github.com/atlantis-devs/dependabump/compare/v1.4.10...v1.4.11) (2021-10-25)


### Bug Fixes

* ensure minor bumps actually are only minor bumps ([4ba3a57](https://github.com/atlantis-devs/dependabump/commit/4ba3a57482bb12fc14dff3332907995d35157b5e))

## [1.4.10](https://github.com/atlantis-devs/dependabump/compare/v1.4.9...v1.4.10) (2021-10-25)


### Bug Fixes

* don't include double quotes in filter strings ([b242e4d](https://github.com/atlantis-devs/dependabump/commit/b242e4daba1adba817cb3c10e1135b3bb659a618))

## [1.4.9](https://github.com/atlantis-devs/dependabump/compare/v1.4.8...v1.4.9) (2021-10-19)


### Bug Fixes

* **action:** ensure filter and reject flags are correctly escaped ([347e2ec](https://github.com/atlantis-devs/dependabump/commit/347e2ecee8dc3ae070cbb77c362bcb4bb7b0080c))

## [1.4.8](https://github.com/atlantis-devs/dependabump/compare/v1.4.7...v1.4.8) (2021-10-14)

## [1.4.7](https://github.com/atlantis-devs/dependabump/compare/v1.4.6...v1.4.7) (2021-10-14)

## [1.4.6](https://github.com/atlantis-devs/dependabump/compare/v1.4.5...v1.4.6) (2021-10-14)

## [1.4.5](https://github.com/atlantis-devs/dependabump/compare/v1.4.4...v1.4.5) (2021-10-14)

## [1.4.4](https://github.com/atlantis-devs/dependabump/compare/v1.4.3...v1.4.4) (2021-10-14)

## [1.4.3](https://github.com/atlantis-devs/dependabump/compare/v1.4.2...v1.4.3) (2021-10-14)

## [1.4.2](https://github.com/atlantis-devs/dependabump/compare/v1.4.1...v1.4.2) (2021-10-14)

## [1.4.1](https://github.com/atlantis-devs/dependabump/compare/v1.4.0...v1.4.1) (2021-10-14)


### Bug Fixes

* **filters:** ensure default values exist for optional filter inputs ([7438eb1](https://github.com/atlantis-devs/dependabump/commit/7438eb1239cb9ca605067915dd6c06601632b2df))

# [1.4.0](https://github.com/atlantis-devs/dependabump/compare/v1.3.2...v1.4.0) (2021-10-14)


### Features

* allow an exclusion list of packages to be defined as an input ([77dd9ea](https://github.com/atlantis-devs/dependabump/commit/77dd9ea1696e6f318ca2fd96033994b6893f92ea))

## [1.3.2](https://github.com/atlantis-devs/dependabump/compare/v1.3.1...v1.3.2) (2021-10-14)


### Bug Fixes

* dont error on no updates ([b2e597f](https://github.com/atlantis-devs/dependabump/commit/b2e597fe34889cda10edca17315d0dbfa929410e))
* dont fail if package lock is missing ([3010ea9](https://github.com/atlantis-devs/dependabump/commit/3010ea995d308863bf1821d15a1f0658d6e01018))
* dont fully replace package locks ([d598517](https://github.com/atlantis-devs/dependabump/commit/d598517d34e453503e72a3f6a3e635feff4895c4))
* make sure lerna bootstrap is in ci mode ([83c223f](https://github.com/atlantis-devs/dependabump/commit/83c223f7c24dc536ef1482dd8bce7f4b51cabe66))
* only add package-lock if package changed ([3a82eb6](https://github.com/atlantis-devs/dependabump/commit/3a82eb6f48fff231dec455345474854a01ed94aa))
* only bump for direct deps ([a1ffa3c](https://github.com/atlantis-devs/dependabump/commit/a1ffa3cefd77aee3ba3b729c6a235d2259644fae))
* only create major updates branch if major updates exist ([5d1e7d5](https://github.com/atlantis-devs/dependabump/commit/5d1e7d54fa7731a3c814857dba36b9b43584606b))
* remove extra double quote ([ba8a25c](https://github.com/atlantis-devs/dependabump/commit/ba8a25c05df376b241309fcd2498e3d3e359b12e))
* remove extra double quote ([a7d386c](https://github.com/atlantis-devs/dependabump/commit/a7d386c88b99d0e122975e5572ea794a88644b86))

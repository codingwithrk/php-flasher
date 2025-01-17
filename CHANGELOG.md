# CHANGELOG for 2.x

## [Unreleased](https://github.com/php-flasher/php-flasher/compare/v2.1.1...2.x)

## [v2.1.1](https://github.com/php-flasher/php-flasher/compare/v2.1.0...v2.1.1) - 2024-10-20

* feature [Laravel] Add `excluded_paths` option. See [PR #203](https://github.com/php-flasher/php-flasher/pull/203) by [yoeunes](https://github.com/yoeunes)

## [v2.1.0](https://github.com/php-flasher/php-flasher/compare/v2.0.4...v2.1.0) - 2024-10-19

* feature [Flasher] Update laravel and symfony configuration documentation . See [PR #201](https://github.com/php-flasher/php-flasher/pull/201) by [yoeunes](https://github.com/yoeunes)
* feature [Flasher] Improve Type Safety and IDE Support with Enhanced PHPDoc Annotations and Stricter PHPStan Validations. See [PR #200](https://github.com/php-flasher/php-flasher/pull/200) by [yoeunes](https://github.com/yoeunes)
* feature [Symfony] Improve configuration descriptions and add examples. See [PR #199](https://github.com/php-flasher/php-flasher/pull/199) by [yoeunes](https://github.com/yoeunes)
* feature [Symfony] Add Symfony Profiler integration for PHPFlasher. See [PR #198](https://github.com/php-flasher/php-flasher/pull/198) by [yoeunes](https://github.com/yoeunes)

## [v2.0.4](https://github.com/php-flasher/php-flasher/compare/v2.0.3...v2.0.4) - 2024-09-22

* bug [laravel] Changed HttpKernel import from `Illuminate\Foundation\Http\Kernel` to `Illuminate\Contracts\Http\Kernel` to use the contract interface instead of the concrete implementation. See [PR #197](https://github.com/php-flasher/php-flasher/pull/197) by [yoeunes](https://github.com/yoeunes)

## [v2.0.3](https://github.com/php-flasher/php-flasher/compare/v2.0.2...v2.0.3) - 2024-09-21

* remove border from flasher container by [yoeunes](https://github.com/yoeunes) 

## [v2.0.2](https://github.com/php-flasher/php-flasher/compare/v2.0.1...v2.0.2) - 2024-09-19

* feature [Flasher] add escapeHtml option for secure HTML escaping in notifications. See [PR #196](https://github.com/php-flasher/php-flasher/pull/196) by [yoeunes](https://github.com/yoeunes)
* feature [Flasher] add Default configuration options. See [PR #183](https://github.com/php-flasher/php-flasher/pull/183) by [AhmedGamal](https://github.com/AhmedGamal)
* feature [Laravel] Refactor middleware to use Symfony's base response class, addressing compatibility issues. See [PR #184](https://github.com/php-flasher/php-flasher/pull/184) by [yoeunes](https://github.com/yoeunes)

## [v2.0.1](https://github.com/php-flasher/php-flasher/compare/v2.0.0...v2.0.1) - 2024-05-23

* bug [#176](https://github.com/php-flasher/php-flasher/issues/176) [Laravel] Correctly disable FlasherMiddleware when `inject_assets` is set to false. See [PR #177](https://github.com/php-flasher/php-flasher/pull/177) by [yoeunes](https://github.com/yoeunes)
* bug [#176](https://github.com/php-flasher/php-flasher/issues/176) [Flasher] Ensure global `timeout` option applies to all requests. See [PR #180](https://github.com/php-flasher/php-flasher/pull/180) by [yoeunes](https://github.com/yoeunes)
* bug [#176](https://github.com/php-flasher/php-flasher/issues/176) [Laravel] Allow disabling of default flash replacement by setting `flash_bag` to false. See [PR #181](https://github.com/php-flasher/php-flasher/pull/181) by [yoeunes](https://github.com/yoeunes)
* bug [#176](https://github.com/php-flasher/php-flasher/issues/176) [Flasher] Ensure `flash_bag` option overrides default values instead of appending. See [PR #182](https://github.com/php-flasher/php-flasher/pull/182) by [yoeunes](https://github.com/yoeunes)

# Debugger

[![Latest Version on Packagist](https://img.shields.io/packagist/v/7at7ot777/debugger.svg?style=flat-square)](https://packagist.org/packages/7at7ot777/debugger)
[![GitHub Tests Action Status](https://img.shields.io/github/actions/workflow/status/7at7ot777/debugger/run-tests.yml?branch=main&label=tests&style=flat-square)](https://github.com/7at7ot777/debugger/actions?query=workflow%3Arun-tests+branch%3Amain)
[![GitHub Code Style Action Status](https://img.shields.io/github/actions/workflow/status/7at7ot777/debugger/fix-php-code-style-issues.yml?branch=main&label=code%20style&style=flat-square)](https://github.com/7at7ot777/debugger/actions?query=workflow%3A"Fix+PHP+code+style+issues"+branch%3Amain)
[![Total Downloads](https://img.shields.io/packagist/dt/7at7ot777/debugger.svg?style=flat-square)](https://packagist.org/packages/7at7ot777/debugger)

A debugging package for Laravel, in the spirit of Laravel Ray: send variables, queries, requests and anything else you want to inspect out of your application while it runs, instead of stopping it with `dd()`. Calls are no-ops when debugging is disabled, so they are safe to leave in place.

> **Status:** early development. The package is scaffolded and the public API described below is the target shape; expect it to change before a `1.0` release.

## Installation

Install the package via composer:

```bash
composer require 7at7ot777/debugger --dev
```

Publish the config file with:

```bash
php artisan vendor:publish --tag="debugger-config"
```

The published config file:

```php
return [
];
```

Publish and run the migrations with:

```bash
php artisan vendor:publish --tag="debugger-migrations"
php artisan migrate
```

Optionally, publish the views with:

```bash
php artisan vendor:publish --tag="debugger-views"
```

## Usage

Send any value out of your application:

```php
use Hathout\Debugger\Facades\Debugger;

Debugger::send($user);
Debugger::send('checkpoint reached', $request->all());
```

Or use the global helper:

```php
debugger($order->total);
```

## Requirements

- PHP 8.4+
- Laravel 10, 11 or 12

## Testing

```bash
composer test
```

Static analysis and code style:

```bash
composer analyse
composer format
```

## Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information on what has changed recently.

## Contributing

Pull requests are welcome. Please run `composer test` and `composer format` before opening one.

## Security Vulnerabilities

Please review [our security policy](../../security/policy) on how to report security vulnerabilities.

## Credits

- [hathout](https://github.com/7at7ot777)
- [All Contributors](../../contributors)

Built on the [spatie/package-skeleton-laravel](https://github.com/spatie/package-skeleton-laravel) template.

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.

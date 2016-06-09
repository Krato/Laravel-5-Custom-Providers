# Laravel 5 Custom Providers

[![Latest Version on Packagist][ico-version]][link-packagist]
[![Total Downloads][ico-downloads]][link-downloads]
[![Software License][ico-license]](LICENSE.md)
[![StyleCI][ico-styleci]][link-styleci]

This package allows you to configure the environment certain service providers and aliases are loaded in.

## Installation
Via [composer](http://getcomposer.org):

```bash
$ composer require infinety-es/custom-providers
```

Or add the package to your dependencies in `composer.json` and run
`composer update` to download the package:

```json
{
    "require": {
        "infinety-es/custom-providers": "^1.0"
    }
}
```

Next, add the `CustomServiceProvider` to your `providers` array in `config/app.php`:

```php
// config/app.php
'providers' => [
    ...
    Infinety\CustomProviders\CustomServiceProvider::class,
];
```

## Usage
You must publish this package's configuration file for it to work correctly. To
do so, run the following command:

```bash
$ php artisan vendor:publish --provider="Infinety\CustomProviders\CustomServiceProvider"
```

After that, you should have see the file `config/providers.php`. 

### Environments
In the `environments` array you can define what environments the provider group
should respond to. You may use an asterisk (`*`) to make that group's providers
and aliases load regardless of the application's environment.

**Note**: You can set your application's environment in either `config/app.php`
under `env` or via your `.env` file.

### Providers
The `providers` array is where you can put the providers you want to have loaded
in the defined environments. This should be pretty straight forward as it is the
same as how you would register service providers in `config/app.php`.

### Aliases
In the `aliases` array you may put all the aliases (facades) you want to register.
As with the providers, this is the same as how you would register aliases in the
default `config/app.php` configuration file.


## Contributing
All contributions (in the form on pull requests, issues and feature-requests) are
welcome. See the [contributors page](../../graphs/contributors) for all contributors.

## License
`sven/env-providers` is licenced under the MIT License (MIT). Please see the
[license file](LICENSE.md) for more information.

[ico-version]: https://img.shields.io/packagist/v/sven/env-providers.svg?style=flat-square
[ico-license]: https://img.shields.io/badge/license-MIT-green.svg?style=flat-square
[ico-downloads]: https://img.shields.io/packagist/dt/sven/env-providers.svg?style=flat-square
[ico-codeclimate]: https://img.shields.io/codeclimate/github/svenluijten/env-providers.svg?style=flat-square
[ico-quality]: https://img.shields.io/scrutinizer/g/svenluijten/env-providers.svg?style=flat-square
[ico-insight]: https://img.shields.io/sensiolabs/i/510c4368-2414-43ae-85e7-486590a4961a.svg?style=flat-square
[ico-styleci]: https://styleci.io/repos/60768133/shield

[link-packagist]: https://packagist.org/packages/sven/env-providers
[link-downloads]: https://packagist.org/packages/sven/env-providers
[link-styleci]: https://styleci.io/repos/60768133

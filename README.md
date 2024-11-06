<div align="center">
    <a href="https://github.com/php-flasher/php-flasher/blob/2.x/docs/palestine.md">
        <img src="https://raw.githubusercontent.com/php-flasher/art/main/palestine-banner-support.svg" width="800px"  alt="Help Palestine"/>
    </a>
</div>

<p align="center">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/php-flasher/art/main/php-flasher-logo-dark.png">
      <img src="https://raw.githubusercontent.com/php-flasher/art/main/php-flasher-logo.png" alt="PHPFlasher Logo">
    </picture>
</p>

<p align="center">
    <a href="https://www.linkedin.com/in/younes--ennaji"><img src="https://img.shields.io/badge/author-@yoeunes-blue.svg" alt="Author Badge"></a>
    <a href="https://github.com/php-flasher/php-flasher"><img src="https://img.shields.io/badge/source-php--flasher/php--flasher-blue.svg" alt="Source Code Badge"></a>
    <a href="https://github.com/php-flasher/php-flasher/releases"><img src="https://img.shields.io/github/tag/php-flasher/flasher.svg" alt="GitHub Release Badge"></a>
    <a href="https://github.com/php-flasher/flasher/blob/master/LICENSE"><img src="https://img.shields.io/badge/license-MIT-brightgreen.svg" alt="License Badge"></a>
    <a href="https://packagist.org/packages/php-flasher/flasher"><img src="https://img.shields.io/packagist/dt/php-flasher/flasher.svg" alt="Packagist Downloads Badge"></a>
    <a href="https://github.com/php-flasher/php-flasher"><img src="https://img.shields.io/github/stars/php-flasher/php-flasher.svg" alt="GitHub Stars Badge"></a>
    <a href="https://packagist.org/packages/php-flasher/flasher"><img src="https://img.shields.io/packagist/php-v/php-flasher/flasher.svg" alt="Supported PHP Version Badge"></a>
</p>

## Table of Contents

- [About PHPFlasher](#about-phpflasher)
- [Features](#features)
- [Supported Versions](#supported-versions)
- [Installation](#installation)
    - [Core Package](#core-package)
    - [Adapters](#adapters)
- [Quick Start](#quick-start)
- [Usage Examples](#usage-examples)
- [Adapters Overview](#adapters-overview)
- [Official Documentation](#official-documentation)
- [Contributors and Sponsors](#contributors-and-sponsors)
- [Contact](#contact)
- [License](#license)

## About PHPFlasher

PHPFlasher is an open-source tool that helps you add flash messages to your web applications. Flash messages are short notifications that provide feedback to users after they perform actions, such as submitting a form or encountering an error. These messages enhance the user experience by informing users about the outcomes of their actions.

PHPFlasher simplifies the process of integrating flash messages into **Laravel** and **Symfony** projects. It uses sessions to store messages, allowing you to set a message on one page and display it on another without complex setup.

## Features

- **Multiple Adapters**: Supports Laravel, Symfony, Toastr, Noty, SweetAlert, and more.
- **Flexible Configuration**: Customize the appearance and behavior of flash messages.
- **Extensible**: Easily integrate with various frontend libraries and frameworks.
- **Intuitive API**: Simple functions to create and manage flash messages.

## Supported Versions

| PHPFlasher Version | PHP Version | Symfony Version | Laravel Version |
|--------------------|-------------|-----------------|-----------------|
| **v2.x**           | ≥ 8.2       | ≥ 7.2           | ≥ 11            |
| **v1.x**           | ≥ 5.3       | ≥ 2.0           | ≥ 4.0           |

> **Note:** If your project uses PHP, Symfony, or Laravel versions below the requirements for PHPFlasher v2.x, please use [PHPFlasher v1.x](https://github.com/php-flasher/php-flasher/tree/1.x).

## Installation

### Core Package

Install the core PHPFlasher package via Composer:

- **For Laravel:**

    ```bash
    composer require php-flasher/flasher-laravel
    ```

  After installation, set up the necessary assets:

    ```shell
    php artisan flasher:install
    ```

  > **Note:** PHPFlasher automatically injects the necessary JavaScript and CSS assets into your Blade templates. No additional steps are required for asset injection.

- **For Symfony:**

    ```bash
    composer require php-flasher/flasher-symfony
    ```

  After installation, set up the necessary assets:

    ```shell
    php bin/console flasher:install
    ```

  > **Note:** PHPFlasher automatically injects the necessary JavaScript and CSS assets into your Twig templates. No additional steps are required for asset injection.

### Adapters

PHPFlasher provides various adapters for different frameworks and notification libraries. Below is an overview of available adapters:

#### Toastr

- [flasher-toastr](https://github.com/php-flasher/flasher-toastr) - Core Toastr Adapter
- [flasher-toastr-laravel](https://github.com/php-flasher/flasher-toastr-laravel) - Laravel Adapter
- [flasher-toastr-symfony](https://github.com/php-flasher/flasher-toastr-symfony) - Symfony Adapter

#### Noty

- [flasher-noty](https://github.com/php-flasher/flasher-noty) - Core Noty Adapter
- [flasher-noty-laravel](https://github.com/php-flasher/flasher-noty-laravel) - Laravel Adapter
- [flasher-noty-symfony](https://github.com/php-flasher/flasher-noty-symfony) - Symfony Adapter

#### Notyf

- [flasher-notyf](https://github.com/php-flasher/flasher-notyf) - Core Notyf Adapter
- [flasher-notyf-laravel](https://github.com/php-flasher/flasher-notyf-laravel) - Laravel Adapter
- [flasher-notyf-symfony](https://github.com/php-flasher/flasher-notyf-symfony) - Symfony Adapter

#### SweetAlert

- [flasher-sweetalert](https://github.com/php-flasher/flasher-sweetalert) - Core SweetAlert Adapter
- [flasher-sweetalert-laravel](https://github.com/php-flasher/flasher-sweetalert-laravel) - Laravel Adapter
- [flasher-sweetalert-symfony](https://github.com/php-flasher/flasher-sweetalert-symfony) - Symfony Adapter

For detailed installation and usage instructions for each adapter, refer to their respective [README.md](https://github.com/php-flasher/flasher-toastr).

## Quick Start

To display a notification message, you can either use the `flash()` helper function or obtain an instance of `flasher` from the service container. Then, before returning a view or redirecting, call the desired method (`success()`, `error()`, etc.) and pass in the message to be displayed.

### Using the `flash()` Helper

```php
class BookController
{
    public function saveBook()
    {
        // Your logic here

        flash('Your changes have been saved!');

        return redirect()->back();
    }
}
```

### Using the `flasher` Service

```php
use Flasher\Prime\FlasherInterface;

class AnotherController
{
    /**
     * If you prefer to use dependency injection
     */
    public function register(FlasherInterface $flasher)
    {
        // Your logic here
        
        $flasher->success('Your changes have been saved!');

        // ... redirect or render the view
    }

    public function update()
    {
        // Your logic here

        app('flasher')->error('An error occurred while updating.'); // ony for laravel

        return redirect()->back();
    }
}
```

## Usage Examples

### Success Message

```php
flash()->success('Operation completed successfully!');
```

### Error Message

```php
flash()->error('An error occurred.');
```

### Info Message

```php
flash()->info('This is an informational message.');
```

### Warning Message

```php
flash()->warning('This is a warning message.');
```

### Passing Options

```php
flash()->success('Custom message with options.', ['timeout' => 3000, 'position' => 'bottom-left']);
```

## Adapters Overview

PHPFlasher supports various adapters to integrate seamlessly with different frameworks and frontend libraries. Below is an overview of available adapters:

| Adapter Repository                                                                      | Description                    |
|-----------------------------------------------------------------------------------------|--------------------------------|
| [flasher-laravel](https://github.com/php-flasher/flasher-laravel)                       | Laravel framework adapter      |
| [flasher-symfony](https://github.com/php-flasher/flasher-symfony)                       | Symfony framework adapter      |
| [flasher-toastr-laravel](https://github.com/php-flasher/flasher-toastr-laravel)         | Toastr adapter for Laravel     |
| [flasher-toastr-symfony](https://github.com/php-flasher/flasher-toastr-symfony)         | Toastr adapter for Symfony     |
| [flasher-noty-laravel](https://github.com/php-flasher/flasher-noty-laravel)             | Noty adapter for Laravel       |
| [flasher-noty-symfony](https://github.com/php-flasher/flasher-noty-symfony)             | Noty adapter for Symfony       |
| [flasher-notyf-laravel](https://github.com/php-flasher/flasher-notyf-laravel)           | Notyf adapter for Laravel      |
| [flasher-notyf-symfony](https://github.com/php-flasher/flasher-notyf-symfony)           | Notyf adapter for Symfony      |
| [flasher-sweetalert-laravel](https://github.com/php-flasher/flasher-sweetalert-laravel) | SweetAlert adapter for Laravel |
| [flasher-sweetalert-symfony](https://github.com/php-flasher/flasher-sweetalert-symfony) | SweetAlert adapter for Symfony |

> **Note:** Each adapter has its own repository. For detailed installation and usage instructions, please refer to the [Official Documentation](https://php-flasher.io).

## Official Documentation

Comprehensive documentation for PHPFlasher is available at [https://php-flasher.io](https://php-flasher.io). Here you will find detailed guides, API references, and advanced usage examples to help you get the most out of PHPFlasher.

## Contributors and sponsors

Join our team of contributors and make a lasting impact on our project!

We are always looking for passionate individuals who want to contribute their skills and ideas.
Whether you're a developer, designer, or simply have a great idea, we welcome your participation and collaboration.

Shining stars of our community:

<!-- ALL-CONTRIBUTORS-LIST:START -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tbody>
    <tr>
      <td align="center" valign="top" width="14.28%"><a href="https://www.linkedin.com/in/younes--ennaji/"><img src="https://avatars.githubusercontent.com/u/10859693?v=4?s=100" width="100px;" alt="Younes ENNAJI"/><br /><sub><b>Younes ENNAJI</b></sub></a><br /><a href="https://github.com/php-flasher/php-flasher/commits?author=yoeunes" title="Code">💻</a> <a href="https://github.com/php-flasher/php-flasher/commits?author=yoeunes" title="Documentation">📖</a> <a href="#maintenance-yoeunes" title="Maintenance">🚧</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://github.com/salmayno"><img src="https://avatars.githubusercontent.com/u/27933199?v=4?s=100" width="100px;" alt="Salma Mourad"/><br /><sub><b>Salma Mourad</b></sub></a><br /><a href="#financial-salmayno" title="Financial">💵</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://www.youtube.com/rstacode"><img src="https://avatars.githubusercontent.com/u/35005761?v=4?s=100" width="100px;" alt="Nashwan Abdullah"/><br /><sub><b>Nashwan Abdullah</b></sub></a><br /><a href="#financial-codenashwan" title="Financial">💵</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://darvis.nl/"><img src="https://avatars.githubusercontent.com/u/7394837?v=4?s=100" width="100px;" alt="Arvid de Jong"/><br /><sub><b>Arvid de Jong</b></sub></a><br /><a href="#financial-darviscommerce" title="Financial">💵</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://ashallendesign.co.uk/"><img src="https://avatars.githubusercontent.com/u/39652331?v=4?s=100" width="100px;" alt="Ash Allen"/><br /><sub><b>Ash Allen</b></sub></a><br /><a href="#design-ash-jc-allen" title="Design">🎨</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://about.me/murrant"><img src="https://avatars.githubusercontent.com/u/39462?v=4?s=100" width="100px;" alt="Tony Murray"/><br /><sub><b>Tony Murray</b></sub></a><br /><a href="https://github.com/php-flasher/php-flasher/commits?author=murrant" title="Code">💻</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://github.com/n3wborn"><img src="https://avatars.githubusercontent.com/u/10246722?v=4?s=100" width="100px;" alt="Stéphane P"/><br /><sub><b>Stéphane P</b></sub></a><br /><a href="https://github.com/php-flasher/php-flasher/commits?author=n3wborn" title="Documentation">📖</a></td>
    </tr>
    <tr>
      <td align="center" valign="top" width="14.28%"><a href="https://www.instagram.com/lucas.maciel_z"><img src="https://avatars.githubusercontent.com/u/80225404?v=4?s=100" width="100px;" alt="Lucas Maciel"/><br /><sub><b>Lucas Maciel</b></sub></a><br /><a href="#design-LucasStorm" title="Design">🎨</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://github.com/AhmedGamal"><img src="https://avatars.githubusercontent.com/u/11786167?v=4?s=100" width="100px;" alt="Ahmed Gamal"/><br /><sub><b>Ahmed Gamal</b></sub></a><br /><a href="https://github.com/php-flasher/php-flasher/commits?author=AhmedGamal" title="Code">💻</a> <a href="https://github.com/php-flasher/php-flasher/commits?author=AhmedGamal" title="Documentation">📖</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://github.com/BrookeDot"><img src="https://avatars.githubusercontent.com/u/150348?v=4?s=100" width="100px;" alt="Brooke."/><br /><sub><b>Brooke.</b></sub></a><br /><a href="https://github.com/php-flasher/php-flasher/commits?author=BrookeDot" title="Documentation">📖</a></td>
    </tr>
  </tbody>
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

## Contact

PHPFlasher is being actively developed by <a href="https://github.com/yoeunes">yoeunes</a>. 
You can reach out with questions, bug reports, or feature requests on any of the following:

- [Github Issues](https://github.com/php-flasher/php-flasher/issues) 
- [Github](https://github.com/yoeunes)
- [Twitter](https://twitter.com/yoeunes)
- [Linkedin](https://www.linkedin.com/in/younes--ennaji/)
- [Email me directly](mailto:younes.ennaji.pro@gmail.com)

## License

PHPFlasher is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).

<p align="center"> <b>Made with ❤️ by <a href="https://www.linkedin.com/in/younes--ennaji/">Younes ENNAJI</a> </b> </p>

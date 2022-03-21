# Lumen 9 simple maintenance mode

[![Build Status](https://travis-ci.com/8ctopus/lumen-9-maintenance-mode.svg?branch=master)](https://travis-ci.com/8ctopus/lumen-9-maintenance-mode)
[![Latest Stable Version](https://poser.pugx.org/8ctopus/lumen-9-maintenance-mode/v/stable)](https://packagist.org/packages/8ctopus/lumen-9-maintenance-mode)
[![Total Downloads](https://poser.pugx.org/8ctopus/lumen-9-maintenance-mode/downloads)](https://packagist.org/packages/8ctopus/lumen-9-maintenance-mode)
[![License](https://poser.pugx.org/8ctopus/lumen-9-maintenance-mode/license)](https://packagist.org/packages/8ctopus/lumen-9-maintenance-mode)

php 8.0.2 Lumen 9.x

## How to install

```sh
composer require 8ctopus/lumen-9-maintenance-mode
```

## How to configure

Add this to your AppServiceProvider or in bootstrap/app.php

```php
$app->register(\oct8pus\MaintenanceMode\Providers\MaintenanceModeServiceProvider::class);
```

Add the up and down commands in app/console/Kernel.php

```php
protected $commands = [
    \oct8pus\MaintenanceMode\Console\Commands\DownCommand::class,
    \oct8pus\MaintenanceMode\Console\Commands\UpCommand::class
];
```

## Maintenance Mode on

```sh
php artisan down
```

## Maintenance Mode off

```sh
    php artisan up
```

## IP based access

Currently only ipv4 and no ip ranges

Add ALLOWED_IPS in your .env file

```ini
ALLOWED_IPS=192.168.1.2,127.0.0.1,136.22.16.0
```

Features planned:
- IP Ranges
- Dynamic DNS IP Filtering

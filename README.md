# Laravel Guzzle

Composer package for Laravel 5.0 and above that provides a consistent method of interacting with Guzzle.

This package is intended to be used to interact with JSON web services but it can also be used with any kind of request endpoint. It provides a basic interface with which to make requests but there is also the option to interact with the underlying Guzzle client instance directly if you need more robust functionality.

## Table of Contents

* [Installation](#installation)
    * [Composer and Service Provider](#composer-and-service-provider)
    * [Middleware Installation](#middleware-installation)
    * [Publish Everything](#publish-everything)
* [Required Environment Variables](#required-environment-variables)
* [Optional Environment Variables](#optional-environment-variables)
* [Resources](#resources)

## Installation

### Composer and Service Provider

#### Composer

To install from Composer, use the following command:

```
composer require csun-metalab/laravel-guzzle
```

#### Service Provider

Add the service provider to your `providers` array in `config/app.php` in Laravel as follows:

```
'providers' => [
   //...

   CSUNMetaLab\Guzzle\Providers\GuzzleServiceProvider::class,

   // You can also use this based on Laravel convention:
   // 'CSUNMetaLab\Guzzle\Providers\GuzzleServiceProvider',

   //...
],
```

### Publish Everything

Finally, run the following Artisan command to publish everything:

```
php artisan vendor:publish
```

The following assets are published:

* Configuration (tagged as `config`) - these go into your `config` directory

## Required Environment Variables

There are currently no required environment variables but there are [optional environment variables](#optional-environment-variables).

## Optional Environment Variables

### GUZZLE_VERIFY_CERT

Should Guzzle verify the server certificate during HTTPS requests? This typically requires the CA cert of the server's chain to be installed on the machine performing the Guzzle request.

During development, this can be set to `false` safely. You may also want to set this to `false` when using WAMP since WAMP tends to have issues with Guzzle when attempting to verify the server certificate.

Default is `true`.

## Resources

### Guzzle

* [Guzzle](http://guzzle.readthedocs.io/en/latest/overview.html)
* [Guzzle Requests](http://guzzle.readthedocs.io/en/latest/quickstart.html#making-a-request)
* [Guzzle Responses](http://guzzle.readthedocs.io/en/latest/quickstart.html#using-responses)
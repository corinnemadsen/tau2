Tau library, version 2
======================

[![Build Status](https://travis-ci.com/theyak/tau2.svg?branch=master)](https://travis-ci.com/theyak/tau2)
![Coverage](https://codecov.io/gh/theyak/tau2/branch/master/graph/badge.svg)

This is a very minimal start to PHP 7 (Note: changed to PHP 5.6) conversion of my standard library that
I use with my own PHP projects. My goal was not to actually re-write a library
of functions that no one uses, but rather to learn about all the PHP tooling
that has come around since the original package was created. Some of my goals
were to learn:

* Installing editorconfig support in vim on Windows (vim-editorconfig vs editorconfig-vim)
* Using and creating tests for Phpunit and looking at various other test suites
* Using PHP CodeSniffer, PHPMD, PHP-CS-Fixer, Psalm, Phan, etc. to check code
* Creating a composer package and putting it on [Packagist](https://packagist.org)
* Setting up continuous integration with Travis-CI.
* PHP 7 language constructs

For a more complete, and PHP 5 compatible version, please use [Tau](https://github.com/theyak/Tau).
I wouldn't really suggest using this any more. It was written circa 2010 with no particular
coding style or methodologies in mind. It's not actively maintained or updated.
Therefore I recommend something like the [Nette Framework](https://nette.org/), which is really
more a set of utility routines than a framework.

Most of the functions in the original library are now better used by more modern libraries.
Here are some examples:
* TauHttp can be replaced with [Requests](https://github.com/rmccue/Requests)
* TauDb can be replaced with [dibiphp](https://github.com/dg/dibi) or [Nette Database](https://doc.nette.org/en/2.4/database)
* TauCache can be replaced with [Stash](http://www.stashphp.com/) or [Nette Caching](https://doc.nette.org/en/2.4/caching)
* Tau::dump can be replaced with [VarDumper](https://symfony.com/doc/current/components/var_dumper.html),
 [Kint](https://kint-php.github.io/kint/), or [Tracy](https://tracy.nette.org/)

Installation
------------

### Install with Composer
[Composer](https://github.com/composer/composer) is the recommended installation method.

```sh
composer require theyak/tau2:dev-master
```
or

    {
        "require": {
            "theyak/tau2": "dev-master"
        }
    }

In your PHP script, use the standard autoloader.

```php
require_once "vendor/autoload.php";
```

### Install source from GitHub
To install the source code:

    $ git clone git://github.com/theyak/tau2.git

And include it in your scripts:

```php
require_once '/path/to/Tau/src/Tau.php';
```

You'll probably also want to register an autoloader:

```php
Theyak\Tau::registerAutoloader();
```

You can optionally enable Tau v1 class names, such as TauCrypt, by passing true
to the autoloader. This isn't recommended but may be useful for compatability
with the original version of Tau.

```php
Theyak\Tau::registerAutoloader(true);
```



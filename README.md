Case converter 
==============

Convert strings among **Camel Case** 🐪, **Snake Case** 🐍and **Kebab Case** 🥙.

* 🔁 automatic case detection
* 🌐 i18n

[![Latest Stable Version](https://poser.pugx.org/jawira/case-converter/v/stable)](https://packagist.org/packages/jawira/case-converter)
[![Total Downloads](https://poser.pugx.org/jawira/case-converter/downloads)](https://packagist.org/packages/jawira/case-converter)
[![License](https://poser.pugx.org/jawira/case-converter/license)](https://packagist.org/packages/jawira/case-converter)
[![composer.lock](https://poser.pugx.org/jawira/case-converter/composerlock)](https://packagist.org/packages/jawira/case-converter)
[![PDS Skeleton](https://img.shields.io/badge/pds-skeleton-blue.svg?style=flat-square)](https://github.com/php-pds/skeleton)
[![Waffle.io - Columns and their card count](https://badge.waffle.io/Jawira/case-converter.svg?columns=all)](https://waffle.io/Jawira/case-converter)

Usage
-----

Automatic conversion:

```php
echo (new Convert('helloWorld'));   // output: hello_world 
echo (new Convert('HelloWorld'));   // output: hello_world 
echo (new Convert('hello_world'));  // output: helloWorld 
echo (new Convert('HELLO_WORLD'));  // output: helloWorld 
```

Explicitly set output case:

```php
$son = new Convert('john_connor'); 
echo $son->toSnake();  // output: john_connor 
echo $son->toCamel();  // output: johnConnor
echo $son->toKebab();  // output: john-connor 
```

Using uppercase versions:

```php
$mother = new Convert('sarahConnor'); 
echo $mother->toSnake(true);  // output: SARAH_CONNOR (aka Screaming Snake Case)
echo $mother->toCamel(true);  // output: SarahConnor (aka Pascal Case)
echo $mother->toKebab(true);  // output: John-Connor (aka Train Case)
```

Handling multilingual strings:

```php
echo (new Convert('DON_RAMÓN_Y_ÑOÑO')); // output: donRamónYÑoño 
echo (new Convert('πολύΚαλό'));         // output: πολύ_καλό 
echo (new Convert('ОЧЕНЬ_ПРИЯТНО'));    // output: оченьПриятно 
```

Notes
-----

* Magic function `__toString` will always print string in Camel case format. 
However, if input string is in Camel case format then Snake case is used.
* If any underscore `_` is found, the input string is considered to be Snake 
Case. If any dash `-` is found, the input string is considered to be Kebab Case. 
Finally, if no `-` nor `_` is found, string is considered to be Camel Case.

Installation
------------

Install using composer:

```sh
$ composer require jawira/case-converter
```

Then import `Convert` class into your code:

```php
<?php
use Jawira\CaseConverter\Convert;
```

Contributing
------------

To contribute to this project please read [CONTRIBUTING.md](./CONTRIBUTING.md).

License
-------

This library is licensed under the [MIT LICENSE](LICENSE.md).

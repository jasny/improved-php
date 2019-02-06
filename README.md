![improved PHP library](https://user-images.githubusercontent.com/100821/46372249-e5eb7500-c68a-11e8-801a-2ee57da3e5e3.png)

Consistent, modern and safe to use functions for PHP.

## Why?

The core libraries of PHP are a mess. Functions have inconsistent names, inconsistent arguments, inconsistent and
sometimes dangerouds return values and deal with errors poorly. This functions have been created decades ago and no
longer live up to current day standards.

While there are many functions, a lot are redundant, while others are missing. For example;
* There are many array functions, but these won't work with other iterables like `ArrayObject`.
* For trimming a string there is `trim`, `rtrim` and `ltrim`. For padding a string there is only `str_pad`, which takes
a `STR_PAD_RIGHT`, `STR_PAD_LEFT` or `STR_PAD_BOTH` as argument.
* For missing functions there are standard patterns to make it work. For instance, to find out if a string contains a
specific substring we use `strpos($string, $substring) !== false`.
* etc

This make it unnecessarily difficult for non-PHP developers to read PHP code and creates a barrier for newcomers to an
otherwise beginner-friendly language.

## What?

All functions are consistently named and take the subject as first argument. The library reduces the number of
functions, opting for the use of constants for options. Options are always the last argument.

The functions throw an Exception in case of an error and return only sensible data.

The library contains of the following packages:

* [iterable](https://github.com/improved-php-library/iterable) - Like array functions, for any iterable. Uses
    Generators.
* [functions](https://github.com/improved-php-library/functions) - Function handling and functional programming.
* [type](https://github.com/improved-php-library/type) - Type checking and casting.

### Roadmap

* [string](https://github.com/improved-php-library/string) - String manipulation.
* array - Limited set of functions that don't make sense for other iterables.

For more high level functionality like database access, filesystem access, image processing, etc, it's recommended to
use an OOP abstraction layer. This is outside of the scope of the improved PHP library.

## How?

All modules code as extension or composer package. The extension is not yet available. The compatibility library can be
installed via

    composer install improved/improved

All functions are in the `Improved` namespace, rather than importing them one by one, it's recommended to alias the
namespace to `i`.

```php
use Improved as `i`;

if (i\type_is($value, '?string') {
    //...
}
```


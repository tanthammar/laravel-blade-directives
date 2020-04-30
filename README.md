# Laravel Blade Directives

[![Latest Version on Packagist](https://img.shields.io/packagist/v/appstract/laravel-blade-directives.svg?style=flat-square)](https://packagist.org/packages/appstract/laravel-blade-directives)
[![Total Downloads](https://img.shields.io/packagist/dt/appstract/laravel-blade-directives.svg?style=flat-square)](https://packagist.org/packages/appstract/laravel-blade-directives)
[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](LICENSE.md)
[![Build Status](https://img.shields.io/travis/appstract/laravel-blade-directives/master.svg?style=flat-square)](https://travis-ci.org/appstract/laravel-blade-directives)

A collection of nice Laravel Blade directives.

## Installation

You can install the package via composer:

```bash
composer require appstract/laravel-blade-directives
```

## Usage

### @filled

the variable isset() and filled() https://laravel.com/docs/7.x/helpers#method-filled

```blade
@filled($variable)
   This will be echoed
@endfilled
```

### @blank

the variable isset() but blank() https://laravel.com/docs/7.x/helpers#method-blank

```blade
@blank($variable)
   This will be echoed
@endblank
```

### @isset
the variable isset() (default php)

```blade
@isset($variable)
   This will be echoed
@endisset
```

### @true

Only show when ```$variable``` isset and true.

```blade
@true($variable)
   This will be echoed
@endtrue
```

Or when you would like to quickly echo

```blade
@true($variable, 'This will be echoed')
```

### @false

Same as ```@true``` but checks for isset and false.

```blade
@false($variable)
   This will be echoed
@endfalse
```

### @null

Only show when ```$variable``` is null.

```blade
@null($variable)
   This will be echoed
@endnull
```

### @notnull

Same as ```@isnull``` but one shows when ```$variable``` is not null.

```blade
@notnull($variable)
   This will be echoed
@endnotnull
```

### @dump and @dd

```blade
@dump($var)

@dd($var)
```

### @mix

Create a HTML element to your Laravel-Mix css or js.
```blade
@mix('/css/app.css')
@mix('/js/app.js')
```
Output:

```blade
<link rel="stylesheet" href="{{ mix('/css/app.css') }}">
<script src="{{ mix('/js/app.js') }}"></script>
```

### @style

Create a ```<style>``` element or ```<link>``` element with a css path.

```blade
@style
    body { background: black }
@endstyle


@style('/css/app.css')
```

### @script

Create a ```<script>``` element with or without a js path.

```blade
@script
    alert('hello world')
@endscript


@script('/js/app.js')
```

### @inline

Load the contents of a css or js file inline in your view.

```blade
@inline('/js/manifest.js')
```


### @pushonce

Same as `@push` but will include content one time only. Useful for repeatable blocks.

First parameter must follow the syntax `stack-name:group-name`.

```blade
@pushonce('js:foobar')
    <script src="{{ asset('/js/foobar.js') }}"></script>
@endpushonce
```

Include pushes with standard `@stack` directive:

```blade
@stack('js')
```

### @routeis

Checks if the current route name is equal to the given parameter. You can use a wildcard like `blog.post.*`.

```blade
@routeis('webshop.checkout')
    Do something only on the checkout
@endrouteis
```

### @routeisnot

Checks if the current route name is not equal to the given parameter. You can use a wildcard like `blog.post.*`

```blade
@routeisnot('webshop.checkout')
    Do something only if this is not the checkout
@endrouteisnot
```

### @instanceof

Checks if the first parameter is an instance of the second parameter.

```blade
@instanceof($user, 'App\User')
    User is an instance of App\User
@endinstanceof
```

### @typeof

Checks if the parameter is of a certain type.

```blade
@typeof($text, 'string')
    Text is a string
@endtypeof
```

### @repeat

Repeat something a specified amount of times.

```blade
@repeat(3)
    Iteration #{{ $iteration }}
@endrepeat
```

### @fa, @fas, @far, @fal, @fab, @fad, @mdi, @glyph

Quickly output an icon with Font Awesome, Material Design Icons or Glyphicon.

```blade
@fa('address-book', 'optional-extra-class')

// for Font Awesome 5 (solid, regular, light, brand, duotone):
@fas('address-book', 'optional-extra-class')
@far('address-book', 'optional-extra-class')
@fal('address-book', 'optional-extra-class')
@fab('address-book', 'optional-extra-class')
@fad('address-book', 'optional-extra-class')

// for Material Design Icons
@mdi('account', 'optional-extra-class')

// for Glyphicons
@glyph('glass', 'optional-extra-class')
```

### @data

Output data-attributes from an array.

```blade
@data(['testing' => 123])
```

### @haserror

Quickly output for classical  ```$errors->has('input_name')``` to determine if any error messages exist for a given field.

```blade
@haserror('input_name')
    This input has an error
@endhaserror
```

## Testing

```bash
composer test
```

## Contributing

Contributions are welcome, [thanks to y'all](https://github.com/appstract/laravel-blade-directives/graphs/contributors) :)

## About Appstract

Appstract is a small team from The Netherlands. We create (open source) tools for Web Developers and write about related subjects on [Medium](https://medium.com/appstract). You can [follow us on Twitter](https://twitter.com/appstractnl), [buy us a beer](https://www.paypal.me/appstract/10) or [support us on Patreon](https://www.patreon.com/appstract).

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.

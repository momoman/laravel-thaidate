![test](https://github.com/momoman/laravel-thaidate/actions/workflows/php.yml/badge.svg)
[![Packagist](https://img.shields.io/packagist/dt/chumpol/thaidate.svg)](https://github.com/momoman/laravel-thaidate/releases)
[![Maintainability](https://api.codeclimate.com/v1/badges/866379571541812960f6/maintainability)](https://codeclimate.com/github/momoman/laravel-thaidate/maintainability)

# <a id="installation"></a> Installation

```
composer require chumpol/laravel-thaidate
```

# <a id="thaidate()"></a> thaidate() function

Display date in Thai using the same PHP built-in [date()](https://www.php.net/manual/en/function.date.php)
function attributes. The date format is as same
as [PHP Datetime Format](https://www.php.net/manual/en/datetime.format.php).

Default Format `j F Y`:

```php
echo thaidate();    
// 25 กุมภาพันธ์ 2564
```

With PHP Date Format:

```php
echo thaidate('วันlที่ j F พ.ศ.Y เวลา H:i:s');
// results: วันพฤหัสบดีที่ 25 กุมภาพันธ์ พ.ศ.2564 เวลา 23:55:29
```

# Laravel Carbon Usage

You can also use `thaidate()` function directly from Laravel carbon instance. It uses Laravel macro feature to add the
functionality as a carbon method.

```php
use Illuminate\Support\Carbon;

Carbon::parse('2021-06-25')->thaidate();
// 25 มิถุนายน 2564

Carbon::parse('2021-06-25')->thaidate('D j M y');
// ศ. 25 มิ.ย. 64
```

This means you can use thaidate() directly from an Eloquent model attributes that is a date attribute as well.

```php
$user->created_at->thaidate();
// 25 มิถุนายน 2564 
```

## License

The MIT License (MIT)

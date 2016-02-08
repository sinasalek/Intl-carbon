Intl-Carbon
=============
PHP Carbon extension with IntlCalendars to support:
* Japanese
* Buddhist
* Chinese
* Persian
* Indian
* Islamic
* Hebrew
* Coptic
* Ethiopic
Calendar types in output.
```php
printf("Right now is %s", IntlCarbon::now()->setCalendar('persian')->toDateTimeString());
//Right now is 1394-04-17 23:38:00
printf("%s",IntlCarbon::now()->setCalendar('islamic')->setLang('ar_UA')->toDateTimeString());
//١٤٣٦-٠٩-٢٢ ٢٣:٣٩:٤٢
```

## Instalation

### With Composer
```
$ composer require amirhabibzadeh/intl-carbon
```

```json
{
    "require": {
        "amirhabibzadeh/intl-carbon": "dev-master"
    }
}
```

```php
<?php
require 'vendor/autoload.php';

use IntlCarbon\IntlCarbon;

printf("Now: %s", IntlCarbon::now());
```

## Todo:
* complete tests
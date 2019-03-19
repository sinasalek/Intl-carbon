MultiCalendarDateTime
=============
PHP Carbon extension with IntlCalendars to support and also pollyfill for Intl:
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

## Dependencies

Before using this package, you should have phpintl on your system.

### PHPintl

#### Installing on Linux (Ubuntu) run the following commands:
```
sudo apt-get install php5-intl
```
You then need to restart Apache
```
sudo service apache2 restart
```
You can also check what extensions are compiled in by running:
```
php -m
```
#### Installing on Linux (Centos)
run the following commands:
```
sudo yum install libicu
sudo yum install libicu-devel.x86_64
sudo /usr/bin/pecl install intl
```
add “extension=intl.so” in your php.ini file.

You can also check what extensions are compiled in by running:
```
php -m
```
#### Installing on OSX

##### Using homebrew:

```
brew update

brew install icu4c
```
##### With PECL
```
sudo pecl update-channels

sudo pecl install intl
```
and add “extension=intl.so” in your php.ini file.

restart the apache.

if you found this error:
Cannot find autoconf. Please check your autoconf installation and the
$PHP_AUTOCONF environment variable. Then, rerun this script.

The solution I came up with was to compile autoconf from source and set the environment variable which points to autoconf required by phpize.

Download autoconf
curl http://ftp.gnu.org/gnu/autoconf/autoconf-latest.tar.gz > autoconf.tar.gz
```
Untar the autoconf archive
tar -xvzf autoconf.tar.gz
```
Configure and make – note the folder un-archived may have a different name.
```
cd autoconf-2.69
./configure
sudo make && sudo make install
```
This installs autoconf to ‘/usr/local/bin/autoconf’. In order to get phpize to work set the PHP_AUTOCONF environment variable to point to the newly installed autoconf.
```
export PHP_AUTOCONF=/usr/local/bin/autoconf
```
Running phpize when attempting to compile a php extension should now work.

#### Installing on Windows

##### Wamp server
on wamp icon click on php -> php extensions -> php_intl then restart the server

## Installation

### With Composer
```
$ composer require amirhabibzadeh/intl-carbon
```

```json
{
    "require": {
        "sinasalek/MultiCalendarDateTime": "dev-master"
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

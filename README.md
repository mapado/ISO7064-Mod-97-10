# Description

Algorithm that calculates number of control, described in ISO 7064, Mod 97 10. Normally used to validate IBAN and nibs of bank accounts.

# Installation

```sh
composer require mapado/iso7064-mod-97-10
```

# Methods

```
class ISO7064Mod97_10
    - encode( string/integer $input )
        return checksum number
    - verify( string/integer $input )
        verify if input are valid with your check digits
    - checkCode( string/integer $input )
        return only check digits of input
    - computeCheck( string/integer $input )
        return mod 97 of input
    - getCheck( string/integer $input )
        return only chek digits of input
    - getData( string/integer $input )
        return value of input without check digits
```

# Example

```php
$service = new Mapado\Iso7064Mod9710\ISO7064Mod97_10();
$number = 107571;
$yourNum = $service->encode($number);
var_dump($yourNum);
//int(10757107)

var_dump($service->verify($yourNum));

$validNumber = '10757107';
$invalidNumber = '10767107';
var_dump($service->verify($validNumber));
var_dump($service->verify($invalidNumber));
```

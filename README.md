# IgAgent

[![Latest version][ico-version]][link-packagist]
[![Software License][ico-license]][link-license]
[![Total Downloads][ico-downloads]][link-downloads]

IgAgent is a user agent generator and parser for Instagram Android.


## Requirements

IgAgent requires PHP 7.4+


## Installation

Simply add a dependency on `mahelbir/ig-agent` to your composer.json file if you use [Composer](https://getcomposer.org/) to manage the dependencies of your project:

```sh
composer require mahelbir/ig-agent
```

Although it's recommended to use Composer, you can actually include files anyway you want.


## Usage

```php
$igagent= new Mahelbir\IgAgent();

//You can set Instagram version, build code and language
$igagent->setIgVersion("224.2.0.20.116");
$igagent->setIgBuild("354065954");
$igagent->setLocale("tr_TR");

//Generate user agent
echo $igagent->userAgent(); //Instagram 224.2.0.20.116 Android (24/7.0; 480dpi; 1080x1920; samsung/Verizon; SM-G935V; hero2qltevzw; qcom; tr_TR; 354065954)
```

```php
$userAgent = "Instagram 151.0.0.23.120 Android (28/9; 480dpi; 1080x2032; HUAWEI/HONOR; LLD-L31; HWLLD-H; hi6250; en_US; 232868034)";
$igagent = new Mahelbir\IgAgent($userAgent);

//You can get user agent components
echo $igagent->getIgVersion(); // 151.0.0.23.120
echo $igagent->getAndroidRelease(); // 28
echo $igagent->getAndroidVersion(); // 9
echo $igagent->getDpi(); // 480dpi
echo $igagent->getResolution(); // 1080x2032
echo $igagent->getManufacturer(); // HUAWEI
echo $igagent->getBrand(); // HONOR (Can be empty)
echo $igagent->getManufacturerWithBrand();// HUAWEI/HONOR
echo $igagent->getModel(); // LLD-L31
echo $igagent->getDevice(); // HWLLD-H
echo $igagent->getCpu(); // hi6250
echo $igagent->getLocale(); // en_US
echo $igagent->getIgBuild(); // 232868034
echo $igagent->getDeviceString(); // 28/9; 480dpi; 1080x2032; HUAWEI/HONOR; LLD-L31; HWLLD-H; hi6250; en_US; 232868034
```


## License

The MIT License (MIT). Please see [License File](LICENSE) for more information.

[ico-version]: https://img.shields.io/packagist/v/mahelbir/ig-agent.svg?style=flat-square
[ico-license]: https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square
[ico-downloads]: https://img.shields.io/packagist/dt/mahelbir/ig-agent.svg?style=flat-square

[link-packagist]: https://packagist.org/packages/mahelbir/ig-agent
[link-license]: LISENCE
[link-downloads]: https://packagist.org/packages/mahelbir/ig-agent
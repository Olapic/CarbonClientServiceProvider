# CarbonClientServiceProvider

[![Build Status](https://img.shields.io/travis/xmarcos/CarbonClientServiceProvider/master.svg?style=flat-square)](https://travis-ci.org/xmarcos/CarbonClientServiceProvider)
[![Coverage Status](https://img.shields.io/scrutinizer/coverage/g/xmarcos/CarbonClientServiceProvider/master.svg?style=flat-square)](https://scrutinizer-ci.com/g/xmarcos/CarbonClientServiceProvider/code-structure)
[![Quality Score](https://img.shields.io/scrutinizer/g/xmarcos/CarbonClientServiceProvider.svg?style=flat-square)](https://scrutinizer-ci.com/g/xmarcos/CarbonClientServiceProvider)
[![Latest Version](https://img.shields.io/packagist/v/xmarcos/carbon-client-service-provider.svg?style=flat-square)](https://packagist.org/packages/xmarcos/carbon-client-service-provider)
[![Software License](https://img.shields.io/packagist/l/xmarcos/carbon-client-service-provider.svg?style=flat-square)](LICENSE)
[![Total Downloads](https://img.shields.io/packagist/dt/xmarcos/carbon-client-service-provider.svg?style=flat-square)](https://packagist.org/packages/xmarcos/carbon-client-service-provider)
[![SensioLabsInsight](https://insight.sensiolabs.com/projects/dafa543d-1b44-4619-8421-1c8c0bf96028/mini.png)](https://insight.sensiolabs.com/projects/dafa543d-1b44-4619-8421-1c8c0bf96028)

A [Silex](https://github.com/silexphp/Silex) Service Provider for the [Carbon (Graphite's backend) Client](https://github.com/xmarcos/CarbonClient).

## Installation

```json
{
    "require": {
        "xmarcos/carbon-client-service-provider": "~2.0"
    }
}
```

## Usage

```php
use Silex\Application;
use xmarcos\Silex\CarbonClientServiceProvider

$app = new Application();
$app->register(new CarbonClientServiceProvider('carbon'), [
    'carbon.params' => [
        'host'      => '127.0.0.1',
        'port'      => 2003,
        'transport' => 'udp',
        'namespace' => 'some.metric.namespace'
    ]
]);

$app['carbon']->send('some.metric', 1);
```

## License

MIT License

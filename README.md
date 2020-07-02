# CarbonClientServiceProvider

A [Silex](https://github.com/silexphp/Silex) Service Provider for the [Carbon (Graphite's backend) Client](https://github.com/xmarcos/CarbonClient).

## Installation

```json
{
    "require": {
        "olapic/carbon-client-service-provider": "~1.0"
    }
}
```

## Usage

```php
use Silex\Application;
use Olapic\Silex\CarbonClientServiceProvider

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

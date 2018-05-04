# Base91

!!! info "Development halted"
    This component is no longer being actively developed, though bugs will be fixed if reported.

A core component, which base91 encodes the payload, you do not need to include it as its included with core.

## Install

Require this package with composer using the following command:

``` bash
$ composer require plinker/asterisk
```

## Client

Creating a client instance is done as follows:


    <?php
    require 'vendor/autoload.php';

    /**
     * Initialize plinker client.
     *
     * @param string $server - URL to server listener.
     * @param string $config - server secret, and/or a additional component data
     */
    $client = new \Plinker\Core\Client(
        'http://example.com/server.php',
        [
            'secret' => 'a secret password',
            'database' => [
                'dsn' => 'mysql:host=127.0.0.1;dbname=asterisk',
                'username' => '',
                'password' => '',
                'database' => '',
                'freeze' => false,
                'debug' => false
            ],
            'ami' => [
                'server' => '127.0.0.1',
                'port' => '5038',
                'username' => '',
                'password' => ''
            ]
        ]
    );
    
    // or using global function
    $client = plinker_client('http://example.com/server.php', 'a secret password', [
        'database' => [
            'dsn' => 'mysql:host=127.0.0.1;dbname=asterisk',
            'username' => '',
            'password' => '',
            'database' => '',
            'freeze' => false,
            'debug' => false
        ],
        'ami' => [
            'server' => '127.0.0.1',
            'port' => '5038',
            'username' => '',
            'password' => ''
        ]
    ]);
   
 
## Methods

Once setup, you call the class though its namespace to its method.


### Command

Execute ASM command.

**Call**


```
$result = $client->asterisk->command('sip show peers');
```

**Response**
```

```

### Get Queue

Connect into AMI and issue asterisk command [queue show *].

**Call**


```
$result = $client->asterisk->getQueue('foo');
```

**Response**
```

```

### Show Channels

Connect into AMI and issue asterisk command [core show channels].

**Call**


```
$result = $client->asterisk->coreShowChannels();
```

**Response**
```
Array
(
    'active_channels' => 0,
    'active_calls' => 0,
    'calls_processed' => 0
}
```

And other methods see: `vendor/asterisk/src/Asterisk.php`

## Testing

There are no tests setup for this component.

## Contributing

Please see [CONTRIBUTING](https://github.com/plinker-rpc/asterisk/blob/master/CONTRIBUTING) for details.

## Security

If you discover any security related issues, please contact me via [https://cherone.co.uk](https://cherone.co.uk) instead of using the issue tracker.

## Credits

- [Lawrence Cherone](https://github.com/lcherone)
- [All Contributors](https://github.com/plinker-rpc/asterisk/graphs/contributors)


## Development Encouragement

If you use this project and make money from it or want to show your appreciation,
please feel free to make a donation [https://www.paypal.me/lcherone](https://www.paypal.me/lcherone), thanks.

## Sponsors

Get your company or name listed throughout the documentation and on each github repository, contact me at [https://cherone.co.uk](https://cherone.co.uk) for further details.

## License

The MIT License (MIT). Please see [License File](https://github.com/plinker-rpc/asterisk/blob/master/LICENSE) for more information.

See [organisations page](https://github.com/plinker-rpc) for additional components.

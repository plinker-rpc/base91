# Base91

!!! info
    This component was originally used as part of the core for encoding the encrypted payload, but it is no longer used as to support the PHP extension version of the client.

Base91 is an advanced method for encoding binary data as ASCII characters. 
It is similar to base64, but is more efficient and compact. 
The overhead produced by base91 depends on the input data. It amounts at 
most to 23% (versus 33% for base64) and can range down to 14%, which typically 
occurs on 0-byte blocks. This makes base91 very useful for transferring larger 
files over binary unsafe connections like e-mail or terminal lines.


## Install

Require this package with composer using the following command:

``` bash
$ composer require plinker/base91
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
            'secret' => 'a secret password'
        ]
    );
    
    // or using global function
    $client = plinker_client('http://example.com/server.php', 'a secret password');
   
 
## Methods

Once setup, you call the class though its namespace to its method.


### Encode

Encode a string.

**Call**


``` php
$result = $client->base91->encode('encode this string');
```

**Response**
``` text
toX<5+UCmUW6GFso^zZ2(.A
```

### Decode

Decode a string.

**Call**


```
$result = $client->base91->decode('toX<5+UCmUW6GFso^zZ2(.A');
```

**Response**
```
encode this string
```

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

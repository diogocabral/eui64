# Node.js EUI64

Node module for dealing 64bit IEEE mac addresses.

[IEEE Spec](http://standards.ieee.org/develop/regauth/tut/eui64.pdf)

[![Build Status](https://travis-ci.org/AdamMagaluk/eui64.png?branch=master)](https://travis-ci.org/AdamMagaluk/eui64)

## Install

`npm install eui64`

## Example


```js

var eui64 = require('eui64');

// Pass a hex string seperated by colons.
var mac = eui64('11:22:33:44:55:66:77:88')

// Pass a hex string seperated by dashes
var mac3 = eui64('11-22-33-44-55-66-77-88')

// Pass a buffer
var mac4 = eui64(new Buffer([0x11,0x22,0x33,0x44,0x55,0x66,0x77,0x88]))

// pass a hex string not seperated with or without leading 0x
var mac5 = eui64('0x1122334455667788')
// or
var mac6 = eui64('1122334455667788')

// Returns null on invalid input
eui64('11:22:33:44:55:bogus') // returns null

```


## Usage

### eui64(input,options)

Parse the given input and return an object or null on failure

  - *input:* String separated by colon/dash or not separated or Buffer. (See examples above).
  - *options:* Object for optional parameters.

    ```
        {
          oui : 36, // OUI bit length 24 or 36
          separator : ':' // Separator to be used in toString()
        }
    ```


### Eui64.toString()

Output current value to string with each octet separated by ':'

### Eui64.toString()

Return buffer of current value

### Eui64.oui()

Return Number representation of the oui, assumes 36 bit oui.


## License

MIT
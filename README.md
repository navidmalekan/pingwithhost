
## Usage

This plugin defines a global `Ping` object.
Although the object is in the global scope, it is not available until after the `deviceready` event.

### Ping a domain
        
```js
document.addEventListener('deviceready', onDeviceReady, false);
function onDeviceReady() {
  var p, success, err, ipList;
  ipList = ['tiste.org'];
  success = function (results) {
    console.log(results);
  };
  err = function (e) {
    console.log('Error: ' + e);
  };
  p = new Ping();
  p.ping(ipList, success, err);
}
```

### Ping an IPv4 address

```js
document.addEventListener('deviceready', onDeviceReady, false);
function onDeviceReady() {
  var p, success, err, ipList;
  ipList = ['192.168.1.254'];
  success = function (results) {
    console.log(results);
  };
  err = function (e) {
    console.log('Error: ' + e);
  };
  p = new Ping();
  p.ping(ipList, success, err);
}
```

### Ping multiple domains or IP addresses

```js
document.addEventListener('deviceready', onDeviceReady, false);
function onDeviceReady() {
  var p, success, err, ipList;
  ipList = ['tiste.org', 'undefineddomain.com', '192.168.1.254'];
  success = function (results) {
    console.log(results);
  };
  err = function (e) {
    console.log('Error: ' + e);
  };
  p = new Ping();
  p.ping(ipList, success, err);
}
```

## Methods

- Ping.ping

## Ping.ping

This method takes the following arguments:

* ipList: an array of domain names or IP addresses
* success: a callback function that handles success
* err: a callback function that handles error

The callback function for success takes one argument, which is a JSON array of results:

```json
[
  {
    "target": "github.com",
    "status": "success",
    "avg": 40.131
  },
  {
    "target": "undefineddomain.com",
    "status": "timeout",
    "avg": 0
  },
  {
    "target": "192.168.1.1",
    "status": "success",
    "avg": 35.654
  }
]
```

The callback function for error takes one argument, which is the error emitted.

### Supported Platforms

- Android


*****

## License

This project is licensed under the [MIT license](https://opensource.org/licenses/MIT). Check the [LICENSE.md file](https://github.com/t1st3/cordova-plugin-ping/blob/master/LICENSE.md).

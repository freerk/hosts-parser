# hosts-parser
hosts file parser

[![Build Status](https://travis-ci.org/imyelo/hosts-parser.svg?branch=master)](https://travis-ci.org/imyelo/hosts-parser)

## Usage
```javascript
var fs = require('fs');
var Hosts = require('hosts-parser').Hosts;
var hosts = new Hosts(fs.readFileSync('/etc/hosts', 'utf8'));
console.log(hosts.toJSON());
/**
[
    {
        "ip": "127.0.0.1",
        "hostname": "localhost"
    }
]
**/
console.log(hosts.resolve('localhost'));
// 127.0.0.1
```

## API
### Hosts(hosts) and Hosts.prototype.parse(hosts)
```
var file = fs.readFileSync('/etc/hosts', 'utf-8');
var hosts = new Hosts(file);
// or (new Hosts()).parse(file);
// return a parsed Hosts object
```

### Hosts.prototype.resolve(hostname)
```
hosts.resolve(hostname);
// return the ip or undefined
```

### Hosts.prototype.toJSON()
```
hosts.toJSON();
// return a json formatted object
```

## What is the Hosts file
[hosts (file)](http://en.wikipedia.org/wiki/Hosts_%28file%29)

## License
the MIT License.

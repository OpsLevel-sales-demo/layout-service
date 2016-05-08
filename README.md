# log4js-json-layout
provides a slim and easy to use json-layout for log4js-node (https://github.com/nomiddlename/log4js-node)

# installation
```
npm install jog4js-json-layout
```

# usage
layout should be type 'json'

currently we support include options only, array of items is expected
log object will contain these properties : ["startTime","categoryName","data","level"]

```
var log4js = require('log4js');
var jsonLayout = require('jog4js-json-layout');

log4js.layouts.addLayout('json', jsonLayout);

appenders = [{
    type: 'console',
    layout: {
        type: 'json',
        include: ['startTime', 'categoryName']
    }
  }
];

```
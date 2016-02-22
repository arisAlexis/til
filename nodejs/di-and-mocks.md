Dependency Injection in node is more straightforward than in other languages such as Java that has very complicated DI frameworks
In node you can use a variety of tools for stubbing functions or variables such as [rewire](https://github.com/jhnns/rewire). 

With require you can stub functions in modules by doing:
```javascript
var myModule = rewire('./myModule');
myModule.__set__({
    console: {
        log: function () { /* be quiet */ }
    },
    process: {
        argv: ["testArg1", "testArg2"]
    }
});
```

For more complicated scenarios and complex module loading there is [mockery](https://github.com/padraic/mockery). With this
you can completely redirect all require calls to serverMock.js instead of server.js for example when doing `require('./server.js');`

A custom scenario would be that:

1. Our test requires app.js
2. app.js requires usersRouter.js
3. usersRouter.js requires userService.js
4. userService.js requires io.js

and we want to mock io.js. Actually we want to redirect completely to another module file like that:

```javascript
const mockery = require('mockery');
mockery.enable({
  useCleanCache: true,
  warnOnReplace: false,
  warnOnUnregistered: false,
});
mockery.registerAllowable('../../js/app'); //this quiets the warnings because the load happens after mockery starts up
mockery.registerSubstitute('../io.js', '../../test/integration/ioMock.js');
```

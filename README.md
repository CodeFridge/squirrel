# squirrel

Squirrel is a helpful node module that allows you to optionally include packages (via [optionalDependencies](http://npmjs.org/doc/json.html#optionalDependencies)) into your application for runtime use rather than using [dependencies](http://npmjs.org/doc/json.html#dependencies).

If you are using `optionalDependencies` in your application trying "squirreling" them rather than requiring them.  (__NOTE:__ Squirreling is an asynchronous operation):

```js
var squirrel = require('squirrel');

squirrel('coffee-script', function(err, coffee) {
    // do something magical with coffeescript...
});
```

If you need multiple modules, then squirrel is happy to play in a way similar to the way AMD module loaders do:

```js
squirrel(['coffee-script', 'jade'], function(err, coffee, jade) {
    // do something with both coffeescript and jade...
});
```

## Squirrel Options

A squirrel's got to have options.  The demands on the modern squirrel mean that having options is important, and this squirrel is not different.  Here are the options that squirrel supports in a 2nd (optional) argument:

- allowInstall (default: false) - whether or not the user should be able to install the requested package on demand.  This is disabled by default to protect against console prompting when using squirrel in web application environments.


The default options can be modified through modifying them in the `squirrel.defaults` object.


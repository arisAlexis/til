from the docs:

Note: the data option passed to Ractive.extend can be an object rather than a function, but this is discouraged as it can cause mutability-related bugs:

```
var BuggyComponent = Ractive.extend({
  data: {
    user: { name: 'Alice' }
  }
});

var ractive1 = new BuggyComponent();
var ractive2 = new BuggyComponent();

ractive1.set( 'user.name', 'Bob' );
console.log( ractive2.get( 'user.name' ) ); // Bob, not Alice!
```

**ignore at your own risk**. This means that if you have multiple components like posts and each one does something like 
`this.set('myvar',true);` all of the posts will have this var true!

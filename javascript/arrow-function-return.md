in order to have an arrow function that constructs just an object and returns it and avoid unecessary code like:  
```javascript
.then((res) => {
     return { total: parseInt(res[0].total) };
   });
```

we can parenthesize the expression like that:  
`params => ({foo: bar})`

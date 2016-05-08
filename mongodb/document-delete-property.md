In mongo documents deleting properties doesn't work and doesn't report any errors.  
`Reflect.deleteProperty(user,'password');` returns true but does not actually remove the property.

Use the following code:  
```javascript
const retUser = Object.assign({},user.toObject());
Reflect.deleteProperty(retUser,'password');
```

When using an async function to iterate an array , using `forEach` will just dispatch async functions but will return immediately. 
Using `for..of` works as expected.It is a babel transpilation issue.

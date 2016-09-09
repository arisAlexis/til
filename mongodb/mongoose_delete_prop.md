when using Mongoose ORM with Node, you cannot delete a property from a Mongoose Model like in normal objects.  
Solution is to call `toObject()` function first to convert it.

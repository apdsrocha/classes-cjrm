# Objects

> JavaScript objects can be understood as representations of objects in real life, as they have characteristics (properties) and are capable of performing actions (methods).

**For example**

Object: user of a web application
Property: email, username and age
Actions: login method, logout method

>>Objects make it possible to create data structures that represent certain elements of our code or our web applications. JavaScript also has some objects attached to it (for example, `date` or` math`). There are a few different ways of creating objects.

## Object Literal

To create an object literal, we use `{ }`, and within those, we assign properties and values.
```
let user = {
  name: 'John',
  age: 31,
  email: 'john@gmail.com'
  blogPosts: ['My first post', 'My second post']
}
```
To access these properties, we can use dot notation or square brackets
```
user.name
// John

user[name]
// John
```
To modify values, simply subscribe to the properties
```
user.name = 'Jose'
user[name] = 'Juan'
```
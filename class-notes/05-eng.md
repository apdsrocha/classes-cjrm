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

To add actions (methods), create a property that stores a function. To access this method, it is necessary to invoke this property with `()` (just like any other function).

```
let user = {
  login: function() {
    console.log('User logged in')
  }
}

user.login()
```

## Objects in Arrays

Storing objects inside arrays is possible and often seen. It is likely when obtaining data from an API or database that it follows the array format with objects.
```
let user = {
  name: 'John',
  blogPosts: [
    { title: 'Pumpkin Soup', likes: 30 },
    { title: '4 mashed potatoes recipes', likes: 45 }
  ],
  logBlogPosts () {
    this.blogPosts.forEach(post => {
      console.log(post.title, post.likes)
    })
  }
}

user.logBlogPosts()

// Pumpkin Soup 30
// 4 mashed potatoes recipes 45
```

## Math Object

The Math Object is one of several built-in objects in the language. It offers a number of methods and properties.

**Example of properties**
```
console.log(Math.PI)
console.log(Math.E)

// 3.141592653589793
// 2.718281828459045
```

**Example of methods**

To round the number using the standard convention (if the decimal place is up to .4, round down, if the decimal place is .5 and bigger round up) we can use the `Math.round()` property:
```
const roundNumber = 7.7

console.log(Math.round(roundNumber))

// 8
```

To round the number down, we can user `Math.floor()`:
```
const roundDown = 5.9

console.log(Math.floor(roundDown))

// 5
```

To round the number up, we can use `Math.ceil()`:
```
const roundUp = 3.2

console.log(Math.ceil(roundUp))

// 4
```

To remove the decimal part and return the integer we can use `Math.trunc()`:
```
const roundInteger = 8.8

console.log(Math.trunc(roundInteger))

// 8
```

To generate a random number between 0 e 1 we can use `Math.random()`:
```
const randomNumber = Math.random()

```
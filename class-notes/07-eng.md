# 'this'

> The reserved key-word `this` is a context object, and represents the context where the code is currently being executed. Depending on where or how it is used, its value may change.

```
let user = {
  name: 'John',
  age: 31,
  email: 'john@email.com',
  city: 'Sao Paulo',
  blogPosts: ['Chicken Potpie', '4 mashed potato recipes'],
  login: function () {
    console.log('User logged in')
  },
  logout: function () {
    console.log('User logged out')
  },
  logBlogPosts: function() {
    // the way to have access to the properties is through `this`

    this.blogPosts.forEach(post => {
      console.log(post)
    })
  }
}

user.logBlogPosts()
// Chicken Potpie
// 4 mashed potato recipes
```

**Note that you must use function declarations for `this` to refer to the object in which the method is created.** 

`this` works differently within an arrow function. The value of `this` references the object at the point of invoking the method.

Still, there's a way of reducing the syntax for the function declaration. The alternative is removing the word `function` and the colon:
```
let user = {
  login () {
    console.log('User logged in')
  }
}
```
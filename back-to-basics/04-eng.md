# Functions

> Functions are part of the data type "object" and their role is to allow the creation of a block of code that can be invoked and executed whenever we want. It is useful for declaring a certain code once inside the function block and executing it whenever necessary.

> We can pass values along to the functions and these values will be used to produce a given output.



Here's how to create a function declaration (where we give the function name):
```
function sayHi() {
  console.log('hi')
}

// we have declared but not invoked the function, that is, nothing happens.
```

What actually invokes the function is the use of `()`.
```
sayHi()

// hi

```

We can also create a function expression (where we assign a function to a variable):
```
const showFood = function() {
  console.log('pizza')
}

showFood()
// pizza
```

What is the difference between the two types? The main one is `hoisting`, that is, the function is being pulled upwards. When we use function declaration anywhere in the code, JavaScript pulls the creation of that function (underneath the hood) to the top of the file.
```
sayHi()

function sayHi() {
  console.log('hi')
}

// there is no error in the code, hoisting causes the function to be pulled up.
```

In the case of function expressions, they exist from the moment they are created.
```
showFood()

const showFood() {
  console.log('pizza')
}

// this throws an error, as it is not possible to invoke a function that does not yet exist.
```

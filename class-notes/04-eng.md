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

## Arrow Functions

> They are one of the additions to modern JS, and one of their uses is to make the syntax shorter and more concise.

```
// Traditional Function syntax 

const double = function(number) {
  return number * 2
}

// let's change to the arrow function syntax.
```


>> 1st: It's not necessary to use the word `function`
```
const double = (number) => {
  return number * 2
}
```

>> 2nd: If you have only one parameter, you don't need to use `()`, but if you have more than one parameter, or no parameter, or you want to use the default value, `()` are mandatory again.
```
const double = number => {
  return number * 2
}
```

>> 3rd: When the code block contains only one line returning a value, we can eliminate the brackets and the word `return`, leaving everything in only one line.
```
const double = number => number *2
```
**Note - we're talking about returning an expression: any piece of code that results in a value. That is, code blocks (if, or switch for example are not expressions that result in a value).**

## Methods

> Methods are also functions, but they are invoked differently: through dot-notation. They are functions associated with objects or data types such as strings.  Methods are created directly on the object or on the data type itself (functions are created on their own).

```
const name = 'ana'

name.toUpperCase(name)

\\ toUpperCase is a string method.

```

## ForEach

> `forEach` is an array method for iteration. It works as a `for`, but in a more elegant and functional way. Its invocation requires a callback function as an argument. We can use three parameters in `forEach`: the array item, its index and the total array.

**Note: callbacks are functions that are passed along as arguments to other functions or methods when they're invoked.**
```
const fruits = ['apple', 'banana', 'watermelon']

fruits.forEach( (fruit, index, array) => {
  console.log( index, fruit, array )
})

// 0 "apple" (3) ["apple", "banana", "watermelon"]
// 1 "banana" (3) ["apple", "banana", "watermelon"]
// 2 "watermelon" (3) ["apple", "banana", "watermelon"]
```

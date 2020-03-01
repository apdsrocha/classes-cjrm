# Data Types

In JavaScript there are 8 data types

> Number (whole numbers or decimals)

> String (chain of characters, meaning, text)

> Boolean (indicates true or false)

> Null (value not yet set by the user)

> Undefined (value not yet set by JS)

> Object (complex data structures - arrays, dates, literals, etc)

> Symbol (used with objects)

> BigInt (used to manipulate larger numbers)


## 1) Strings
**Strings are kept between single or double quotes** 
```
'hello, world'
"hello, world"

```
Strings can be combined by using  `+`
```
let hello = "hello"
let world = "world"

let greeting = hello + ' ' + world
```
To access a certain character we can open and close [ ] to specify the location we want. JS is a zero-based language, so we start counting with position zero.

If we want to access the index position of `o` in `hello`:

```
greeting[4]
```

**Strings have properties and methods:** 
> To specify a property we use  `.` followed by the property.


`.length` is a property that counts the number of characters in a string.
```
let name = 'Ana'
name.length // 3
```

> Functions that are restricted to an object scope are named method - and like functions, they execute a specific action.

`.toUpperCase()` turns every character in a string into upper case, without altering the original string. 
```
name.toUpperCase() // ANA
```

`.toLowerCase()` turns every character in a string into lower case, without altering the original string. 
```
name.toLowerCase() // ana
```

`.indexOf('argument')` searches for the index where the argument passed as a parameter shows up in a string. Returns the index and doesn't alter the original string in any way.
```
name.indexOf('n') // 1
```

`.lastIndexOf('argument')` searches for the last occurance of the string passed on as an argument. Returns the index of that occurance.
```
name.lastIndexOf('a') // 2
```

`.slice( index1, index2 )` returns a slice of the string that begins in the first argument (which should be an index number) and goes up to one index value before the last argument (which should also be an index number). This method doesn't alter the original string.
```
name.slice(0, 2) // An
```

`.replace( index1, index2 )` substitutes a character of a string by another. The first argument is the string that should be searched for, and the second one is the string it should replace it with. It doesn't alter the original string in any way. Notice that this method only alters the first occurance (to alter multiple occurances we should use Regex).
```
name.replace('n', 'd') // Ada
```

## 2) Numbers
**Numbers can be stored in variables - decimals should use  `.` instead of `,`**
```
const radius = 10
const pi = 3.14
```
> Arithmetic Operators

`*` multiplier

`+` addition

`-` subtraction

`/` division

`**` exponent

> Order of operation: obeys the same rules as math (1st parentheses, 2nd exponents or roots, 3rd multiplication or division, 4th addition and subtraction)

> Increment operators
```
let postLikes = 10
postLikes++ 
// postLikes = postLikes + 1 
// 11

postLikes--
// postLikes = postLikes - 1 
// 9

postLikes += 10
// postLikes = postLikes + 10 
// 20
```

> Operations that don't result in a number: NaN
```
(7 / 'hi') // NaN
```

> String Concatenation with numbers: JS converts numbers to string, so the result of a concatenation between a string and a number will always be a string.
```
const likesMessage = 'The post has' + postLikes + 'likes.' // 'The post has 10 likes.'
```


## 3) Objects
**Arrays are used to store a list of values that usually have some relation to each other**
```
let heroes = ['Batman', 'Catwoman', 'Iron Man']

```

To change values writing over given positions in the array:
```
heroes[2] = 'SpiderMan'

```
It's possible to store different types of data in the same array:
```
const randomArray = ['Parker', 'Diana', 19, 18]

```
**Array properties and methods**

`.length` returns the amount of items in an array
```
let heroes = ['Batman, 'Catwoman', 'Iron Man']
heroes.length // 3
```

`.join()` returns a new string with every item in the array separated by a comma. It can receive an optional argument that acts as a separator instead of the comma.
```
heroes.join() // Batman,Catwoman,Iron Man

heroes.join('|') // Batman|Catwoman|Iron Man

```

`.indexOf()` returns the index of the given argument. If the argument doesn't exist in the array, it returns -1
```
heroes.indexOf('Batman') // 0

heroes.indexOf('Hulk') // -1

```

`.concat()` joins the array which invoked the method adding whatever was passed on as an argument. Doesn't alter the original array. 
```
heroes.concat(['SpiderMan', 'Wolverine']) // ['Batman, 'Catwoman', 'Iron Man', 'SpiderMan', 'Wolverine']

```

`.push()` includes the items passed on as arguments in the original array. Returns the new number of items in the array after adding the arguments. It changes the original array, resulting in a value mutation.
```
heroes.push('Cyclops', 'Superman') // ['Batman, 'Catwoman', 'Iron Man', 'Cyclops', 'Superman']

```

`.pop()` removes the last item in the array and returns that item. Also modifies the original array.
```
heroes.pop() // 'Superman'

```

## 4 & 5) Null and Undefined

>These two types are similar and both represent the lack of value. The difference between them is that `null` needs to be intentionally atributed. 

Every time we declare a variable without atributing any value, JavaScript sets it to `undefined` 
```
let emptiness 
console.log(emptiness)  // undefined
```

If we try to use `undefined` in a numerical expression, we get `NaN`
```
emptiness + 3 // NaN
```

To purposelly indicate that a variable doesn't have a value stored in it, `null` should be used. 
```
let emptiness = null
console.log(emptiness)  // null

```

When we execute a mathematical operation using  `null`  it is interpreted as zero and doesn't throw an error.
```

emptiness + 3 // 3
```
## 6) Booleans

> `true` and `false` are reserved words and data types that are used to verify conditions - whether a piece of code evaluates to true or false. 

```
const email = 'brucewayne@gmail.com'
const includes = email.includes('@')

console.log(includes)  // true
```

**Comparison Operators**

These are used to compare a value to another, and the comparison should return a boolean.

```
const age = 31

console.log(age == 31)  // true
```

Remember: `=` means attribution and `==` means comparison.

To write "different than", you should use `!=` 
```
console.log(age != 31)  // false
```

Other number comparisons:
```
console.log(age > 10)  // true
console.log(age < 10)  // false
console.log(age <= 31>)  // true
console.log(age >= 31>)  // true

```

String comparisons:
```
const name = 'ana'

console.log(name == 'ana')  // true
console.log(name == 'Ana')  // false
console.log(name > 'bel' )  // false ('a' comes before 'b')
console.log(name > 'Ana' )  // true (lowercase comes before upper case)

```

**Strict comparisons**

When we used `==` we run the risk of having an equality in an expression that involves different types.

```
// 'Equal to' and 'different than'
console.log( 31 == 31 ) // true
console.log( 31 == '31' ) // true
console.log( 31 != 31 ) // false
console.log( 31 != '31' ) // false

```
To avoid this, we use `===` to have a strict comparison.
```
// 'Equal to, and with the same type' and 'different than, and with the same type'
console.log( 31 === 31 ) // true
console.log( 31 === '31' ) // false - since we're checking value AND type

console.log( 31 !== 31 ) // false
console.log( 31 !== '31' ) // true

```
That's why it's safer to stick with strict comparisons.
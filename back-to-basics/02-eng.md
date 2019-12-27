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
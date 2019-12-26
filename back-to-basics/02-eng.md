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

> Functions that are restricted to an object scope are named method - and like functions, they execute a specified action.

`.toUpperCase()` turns every character in a string into upper case, without altering the original string. 
`.toLowerCase()` turns every character in a string into lower case, without altering the original string. 
`.indexOf('argument')` searches for the index where the argument passed as a parameter shows up in a string (doesn't alter the original string).
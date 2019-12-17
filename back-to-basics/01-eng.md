
# variables
> Variables are meant to store a value so that you can use it later.

Here are some of the ways you can declare a variable:

## 1) let
```
let age = 31
let currentYear = 2019
```

`age` becomes a container for the value of `31` 

**important:** `=` should be understood as "receives" and not as "equal".

**important 2:** to make an attribution you don't have to declare a variable again (using let), just write the name o f the variable that you've already declared and atribute a new value to it. 

``` 
age = 33
```


## 2) const
```
const points = 100
```
A variable that should not have new values attributed to it is a constant.


**important:**  `let` and `const` were added to ES5, before that  `var` was used (and it allows many attributions) 

## rules when naming variables

1) should be one word only (no spaces)
``` 
age = 33
//not 'my age' 
```

2) if you plan on using more than one word, it should use camelCase syntax => the first word begins with a lowercase, followed by a words with a uppercase letter.
``` 
currentYear = 2019
```

3) it can only contain letters, numbers, underscore and dollar sign as symbols. It can't start with a number.

4) some words are reserved and can't have values attributed to them.

5) give meaningul names => must be easy to understand what theuy do.

# to add comments

```
/* comments with 
many 
lines
*/

// comments with only one line

```


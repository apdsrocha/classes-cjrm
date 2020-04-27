# Introduction to Regular Expressions (Regex)

> To check for string patterns, we can use regular expressions (or Regex). They are used in several programming languages and are standards that allow you to check if a certain character combination is present in a string. The first step is to define what type of pattern the string should check (for example: how many characters? Which types? Upper or lower case?) Having this, we write the expression that will match our criteria, and can, for example, check with whatever the user wrote in a text input.

Using the site [Regex 101](https://regex101.com/), you must first change the language in the 'Flavor' listing by clicking on *ECMAScript (Javascript)*. In the first input we write the REGEX that we are going to check for and in the second field we add the string we want to test.


--> A Regex begins with a `/`  
`/javascript`  
Match: `javascript`  
Match: `asdfjavascriptasdf`  
  
  \
--> A Regex that does not allow characters before or after the string:  
`/^javascript$`  
Match: `javascript`  
  
  \
--> To match any letter from 'a' to 'z' we use a character set '[]':  
`/^[a-Z]$`  
Match: b  
(expression matches only 1 character, 'bc' is not a match)  
  
  \
--> To match lowercase and uppercase characters:  
`/^[a-zA-Z]$`  
Match: B  
(matches only with strings that have one character)  
  
  \
--> To match more than one character we use a quantifier '{}':  
`/^[a-zA-Z]{6,10}$`  
Match: asDFG  
  
  \
--> To match letters and numbers:  
`/^[a-zA-Z0-9]{6,10}$`  
Match: asDFG82  
  
  \
--> To match any character:  
`/.{6,10}$`  
Match: 123@[  
  
  \
To read more about it, check the [Regex in MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions).

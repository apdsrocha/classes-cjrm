# Flux control

When writing more complex programs it is often necessary to decide the next action to be performed, or to execute the same piece of code many times over. That means we are controling the flow of our program.


> Loops

Example: run through an array and perform an action to each item.

> Conditional Statements 

Example: if a condition is true, do something.

## For Loop

The purpose of a `for` loops is to repeatedly execute a given piece of code, provided the condition is true.

```
for( let i=0; i < 5; i++ ) {

}
```
* Everything inside '{}' is called a 'code block'
* `let i = 0`  starts the counter (how many times the block has already been executed)
* `i <5` is the condition, if it results in `true` the  code block is executed, otherwise it is ignored.
* i ++ is the increment; an expression executed at the end of the block, increasing the variable `i`.

```
for( let i=0; i < 5; i++ ) {
  console.log(`Number running in the loop: ${i}`);
}

// Number running in the loop: 0
// Number running in the loop: 1
// Number running in the loop: 2
// Number running in the loop: 3
// Number running in the loop: 4

```


## While Loop

A different way of creating a repetition loop is through `while`. Keep in mind that the increment variable must be declared outside the repetition structure, and undergo an increment within it.

```
let i = 0 // has to be declared before the 'while'

while( i < 5 ) {
  console.log(`Number running in the loop: ${i}`)
  i++ // has to be incremented to avoid an infinite loop.
}

// Number running in the loop: 0
// Number running in the loop: 1
// Number running in the loop: 2
// Number running in the loop: 3
// Number running in the loop: 4

```
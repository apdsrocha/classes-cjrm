# Scope

> Scope is the area where the value of a variable is available to be used.

When the variable is created at the root of the document (outside a code block) it has a global scope, that is, it can be accessed in any part of the document.
```
let age = 31

if(true){
  console.log(`inside first code block: ${age}`)
}

console.log(`outside code block: ${age}`)

\\ inside first code block: 31
\\ outside code block: 31

```

We can also change the value of the variable within a code block. Therefore, we changed the value of the variable in its global scope.
```
let age = 31

if(true){
  age = 41
  console.log(`inside first code block: ${age}`)
}

console.log(`outside code block: ${age}`)

\\ inside first code block: 41
\\ outside code block: 41

```

We can create variables with the same name, as long as it's not within the same scope. This way, a local scope is created for the variable within a given code block. The variable declared in local scope can only be accessed in this same scope and does not work in other contexts.
```
let age = 31

if(true){
  let age = 41
  console.log(`inside first code block: ${age}`)
}

console.log(`outside code block: ${age}`)

\\ inside first code block: 41
\\ outside code block: 31

```

In the case of nested blocks, the value accessed is always that of the closest context.
```
let age = 31

if(true){
  let age = 41
  console.log(`inside first code block: ${age}`)
  
  if(true){
     console.log(`inside second code block: ${age}`)
  }
}

console.log(`outside code block: ${age}`)

\\ inside first code block: 41
\\ inside second code block: 41
\\ outside code block: 31
```
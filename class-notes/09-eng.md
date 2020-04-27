# DOM Events

> Most of the time the changes and manipulations we make are reactions to the user's actions on the page. For example, if the user clicks on a trash can, something is deleted. There are several possible events: mouse, keyboard, submit events, etc.

## Click events

After obtaining the reference of the element where we want the event to happen, we can add an `event listener`. This way, the element keeps "listening" for when the event is triggered. The third step is to implement a callback function to take place when the event happens (for example, when the button is clicked)

```
button = document.querySelector('button')
\\ get button reference

button.addEventListener('click', () => { console.log('Clicked the button')})
\\ adds the event we want to watch out for (1st parameter) and the callback function that should occur after the click (2nd parameter).
```

For a list of the different `event listeners`, [click here](https://developer.mozilla.org/en-US/docs/Web/Events).


> When an event happens in the browser, the browser makes an object available within the callback function of `addEventListener`. That object is` event` and it has information about the event that happened. An example is the `target` property, which stores the reference of the element in which the event occurred.

```
lis.forEach( li => {
  li.addEventListener('click', event => {
    console.log(event.target)
  })
})

\\ shows on the console the reference of the `li` that was clicked
```


## Event bubbling

> The element where an event occurred becomes the `target`. When this happens, JS looks for whether there is an `eventListener` in that event to trigger the linked callback function. But that's not all that happens: the event is propagated from the `target` where it happened through the DOM tree all the way to the top.

```
li.addEventListener('click', event => {
  const clickedElement = event.target
  clickedElement.remove()
})
// when clicked, the li element will be removed...

ul.addEventListener('click', () => console.log('event listener was triggered'))
// ...and the console shows the message, because ul (li's parent element) had its "event listener" propagated.

```

This propagation is called an `event bubbling`. The event starts at the `target` (element where the event was added), and propagates to the parents, causing the event callbacks that are assigned to these parents to be triggered as well.

Through the `stopPropagation` method of the` event` object, it is possible to prevent the event from moving on to the parent elements.
```
li.addEventListener('click', event => {
  const clickedElement = event.target
  clickedElement.remove()

  event.stopPropagation()
})
// when clicked, the li element will be removed...

ul.addEventListener('click', () => console.log('event listener was trigged'))
// ...and the event will not be propagated. The message on the console will be displayed only if the click occurs on the `ul` element.
```

This is important to avoid unexpected behavior when it comes to event propagation.


## Event delegation

Adding events to each element (for example, using `forEach` to iterate and add events to each element) at scale can affect performance - and therefore is not good practice.

```
ul.addEventListener('click', event => {
  console.log(event.target)
})
// gets the reference of the clicked child elements through the event propagation that is triggered.
```


It is possible to check through the `tagName` property if the click took place on the element you expected.
```
ul.addEventListener('click', event => {
  const clickedElement = event.target

  if(clickedElement.tagName === 'LI') {
  clickedElement.remove() 
  }
})
```


## Events in forms

> Forms exist to capture input information provided by users. An example could be a feedback form - to capture this information we use events - mainly `submit` events. Clicking on a submit button triggers the click event but also triggers a `form submit` event. In this case, we can set up an event listener that reacts to this so when the `form` is sent we can capture this information. Other types of events we can interact with are keyboard events (when the user presses or releases the key).

### The submit event

When we want to listen for a user event it is important to link the listening event to the form (and not to the button, as we have been doing until then). Because what we want is to listen to the sending of information, and not the button (which is just one element of the form).
```
const form = document.querySelector('.signup-form')

form.addEventListener('submit', event => {
  event.preventDefault()
})
// avoids default behavior of reloading the page when submitting
```

To obtain the reference of what was inserted in the form, we can use a few different forms. For example, using the ID in the input tag:
``` 
const form = document.querySelector('.signup-form')
const usernameInput = document.querySelector('#username')

form.addEventListener('submit', event => {
  event.preventDefault()
  console.log(usernameInput.value)
})
// shows the input value on the console.
```

Another way is to use the `form` reference to access the` ID` or `name`.
```
form.addEventListener('submit', event => {
  console.log(form.username.value)
})
```

It is still possible to use `event.target` instead of `form` to access the username and therefore its value.
```

form.addEventListener('submit', event => {
  console.log(event.target.username.value)
})
```



## Keyboard Events

### 'Key Up' Event

> This event will execute a callback function every time a  pressed key is released (or the exact moment the key goes back up).

```
const form = document.querySelector('form')

form.idInput.addEventListener('keyup', event => 
console.log(event.target.value))
// when you press and release the key, the function is executed and the value of the input is displayed on the console.
```

Example of input validation in real time:
```
form.idInput.addEventListener('keyup', event => {
if (isValidUsername) {
  form.idInput.setAttribute('class', 'success')
  return
}
form.idInput.setAttribute('class','error')
})
```
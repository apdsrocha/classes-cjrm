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

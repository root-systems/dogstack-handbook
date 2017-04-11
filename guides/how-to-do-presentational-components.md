# How to do presentational components

## What's a presentational component?

Introduced in ["Presentational and Container Components"](https://medium.com/@dan_abramov/smart-and-dumb-components-7ca2f9a7c7d0), "presentational components" are [React components](https://facebook.github.io/react) that

> - Are concerned with how things look.
> - May contain both presentational and container components inside, and usually have some DOM markup and styles of their own.
> - Often allow containment via this.props.children.
> - Have no dependencies on the rest of the app, such as Flux actions or stores.
> - Don’t specify how the data is loaded or mutated.
> - Receive data and callbacks exclusively via props.
> - Rarely have their own state (when they do, it’s UI state rather than data).
> - Are written as functional components unless they need state, lifecycle hooks, or performance optimizations.
> 
> Examples: Page, Sidebar, Story, UserInfo, List.

## Example presentational component

A presentational component is written as a file in `${topic}/components/${name}`.

We will use:

- [`react`](https://facebook.github.io/react/docs/react-api.html)
- [`react-fela`](https://github.com/rofrischmann/fela/tree/master/packages/react-fela)

Here is an example 'counter' component within the 'count' topic:

```js
// count/components/counter.js

// imports
import React, { Component } from 'react'
import { createComponent } from 'react-fela'
import styles = require('../styles/counter')

// styled components
const Container = createComponent(styles.container)
const Button = createComponent(styles.button, 'button', ['onClick'])
const Input = createComponent(styles.input, props => {
  return <input type='number' />
}, ['value', 'onInput')

// exported component
export default props => {
  const { value, increment, decrement, set } = props

  return <Container>
    <Button
      onClick={handleClick(increment)}
      type='increment'
    >
      +
    </Button>
    <Input
      onInput={handleInput(set)}
    />
    <Button
      onClick={handleClick(decrement)}
      type='decrement'
    >
      -
    </Button>
  </Container>

  function handleClick (action) {
    return ev => action()
  }

  function handleInput (action) {
    return ev => {
      ev.preventDefault()
      action(Number(ev.target.value))
    }
  }
}
```

```js
// count/styles/counter.js

export default {
  container: props => {
    display: 'flex'
  },
  button: props => {
    backgroundColor: buttonColors[props.type]
  },
  input: props => {
    padding: '1rem'
  }
}

const buttonColors = {
  increment: 'green',
  decrement: 'red'
}
```

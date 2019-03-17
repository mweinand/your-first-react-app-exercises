# Exercise 14

## Convert A Component

Components that don't maintain their own state or use React methods other than `render()` can be converted from class syntax components to stateless functional components. This reduces code boilerplate.

In this exercise, you'll convert a component from a function to a class. This is an activity that, until React version 16.8, happened quite often during development.

👉 Start the app for Exercise 14

In a console window, pointed at the root of this project, run `npm run start-exercise-14`.

This should open a browser window pointed at localhost:3000, showing a web app titled "Exercise 14: Convert a Component". If it doesn't, ask your neighbor for assistance or raise your hand.

👉 Open Exercise.js

All of your work for this exercise will take place in Exercise.js.

### Background

In this exercise, we have two components in `Exercise.js` - `Friends` and `FriendProfile`. Neither of these components needs state, and neither needs any React methods other than `render()`. We can convert them both!

### The Process

When converting to a stateless functional component, there are three things that need to be done:

#### 1. Convert the class to a function of the same name

For example,

```jsx
class FriendProfile extends React.Component {
  // render()...
}
```

becomes

```jsx
function FriendProfile(props) {
  // render()...
}
```

#### 2. Remove the render() method

For example,

```jsx
function FriendProfile(props) {
  render() {
    // ...what gets rendered
  }
}
```

becomes

```jsx
function FriendProfile(props) {
  // ...what gets rendered
}
```

#### 3. Convert `this.props` references to `props`.

For example,

```jsx
{
  this.props.name;
}
```

becomes

```jsx
{
  props.name;
}
```

That's all it takes to convert from a class syntax component to a stateless functional one!

👉 Convert the `Friends` component to a stateless functional component

Check your browser to make sure the components are still rendering properly!

If you get stuck, [see a possible solution here](./SOLUTIONS.md#friends-to-stateless).

👉 Convert the `FriendProfile` component to a stateless functional component

Check your browser to make sure the components are still rendering properly!

If you get stuck, [see a possible solution here](./SOLUTIONS.md#friendprofile-to-stateless).

Sometimes, we need to convert the other direction - from stateless functional component to class syntax component.

👉 Convert the `Friends` component back to a class syntax component

Check your browser to make sure the components are still rendering properly!

If you get stuck, [see a possible solution here](./SOLUTIONS.md#friends-to-class).

👉 Convert the `FriendProfile` component back to a class syntax component

Check your browser to make sure the components are still rendering properly!

If you get stuck, [see a possible solution here](./SOLUTIONS.md#friendprofile-to-class).

---

TODO

Extra Credit: https://overreacted.io/how-are-function-components-different-from-classes/

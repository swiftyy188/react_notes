# Components
## What are they?

- They are self contained Javascript and JSX modules that render HTML.
- They have lifecycles from mounting to destroy methods
- They can run functions based on user interactions
- They can be rendered within other components iteratively.

# What is JSX?

- JSX is basically just an upgraded version of HTML
- JSX enables you to interpolate Javascript into your HTML code.
- Example in your render method:

```javascript
render() {
  return(
    <div id="mappable-array">
      {
        this.state.mappableArray.map((a, i) => {
            return(<p>{a} has an index of {i})
        })
      }
    </div>
  )
}
```

# What is state?

- State is self contained within the component
- It is typically a JSON object that stores key values
- You can initialize state with a constructor
- Example in a React Component

```javascript
var TestComponent extends Component {

  constructor(props) {
    super(props)
    this.state = {
      'key': 'value'
    }
  }

  updateState(value, e) {
    this.setState({
      'key': value
    })
  }

}
```

- So basically we can update state with the `setState()` methods
- And we can initialize state a `constructor()`

# Component Lifecyles

- Components have functions that can be declared when a component is added, updated or removed from a view.
- Example component lifecycle states are as follows

```javascript
var TestComponent extends Component {

  componentDidMount() {
    console.log("This is when the component is added to the view...")
  }

  componentDidUpdate() {
    console.log("This is when the component updates...")
  }

  componentWillUnmount() {
    console.log("This is when the component is removed from the view...")
  }

}
```

# Interactions in React Components

- In most case scenarios you can delegate interactions with default `onClick` methods or other default method conventions.
- An example of a click interaction is as values

```javascript
class TestComponent extends Component {

  clickEvent(e) {
    console.log("The p tag has been clicked!")
  }

  render() {
    return(
      <p onClick={this.clickEvent.bind(this)}>Click me</p>
    )
  }

}
```

- In this case scenario when a paragraph tag is clicked. It runs the `clickEvent()` function.
- Recent changes to React require you to `.bind(this)` the React Component to the JSX in order to delegate events to the Component

- We can have more in depth interactions with Components in the context of passing variables or objects to `.bind()` method.

```javascript
class TestComponent extends Component {

  clickEvent(variablePassed, e) {
    console.log("The variable that has been passed is", variablePassed)
  }

  render() {
    return(
      <p onClick={this.clickEvent.bind(this, 1)}>Click me</p>
    )
  }

}
```

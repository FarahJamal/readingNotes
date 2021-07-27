# React and Forms
### Just like in HTML, React uses forms to allow users to interact with the web page.

### Adding Forms in React You add a form with React like any other element:

```
Example:
Add a form that allows users to enter their name:

class MyForm extends React.Component {
  render() {
    return (
      <form>
        <h1>Hello</h1>
        <p>Enter your name:</p>
        <input
          type="text"
        />
      </form>
    );
  }
}
ReactDOM.render(<MyForm />, document.getElementById('root'));
```

### Handling Forms
Handling forms is about how you handle the data when it changes value or gets submitted.

In HTML, form data is usually handled by the DOM.

In React, form data is usually handled by the components.

When the data is handled by the components, all the data is stored in the component state.

You can control changes by adding event handlers in the onChange attribute:

```
Example:
Add an event handler in the onChange attribute, and let the event handler update the state object:

class MyForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = { username: '' };
  }
  myChangeHandler = (event) => {
    this.setState({username: event.target.value});
  }
  render() {
    return (
      <form>
      <h1>Hello {this.state.username}</h1>
      <p>Enter your name:</p>
      <input
        type='text'
        onChange={this.myChangeHandler}
      />
      </form>
    );
  }
}

ReactDOM.render(<MyForm />, document.getElementById('root'));
```


## If you do not want to display the h1 element until the user has done any input, you can add an if statement.

Look at the example below and note the following:

1. We create an empty variable, in this example we call it header.

2. We add an if statement to insert content to the header variable if the user has done any input.

3. We insert the header variable in the output, using curly brackets.


[source](https://www.w3schools.com)


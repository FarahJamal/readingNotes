# Thinking in react.
### to break the mock to component heirarchy you need to:
- think in a app or the thing you'll used as a parts and if you already have a designer you can take a look into the heirarchy he made :) 
- One such technique is the `single responsibility principle`, that is, a component should ideally only do one thing. If it ends up growing, it should be decomposed into `smaller subcomponents.`

### static version of your App.
* building a static version requires a lot of typing and no thinking, and adding interactivity requires a lot of thinking and not a lot of typing
* To build a static version of your app that renders your data model.
 ### : Identify The Minimal (but complete) Representation Of UI State.
 - in this stage you want to define if something state or not: 
   - Is it passed in from a parent via props? If so, it probably isn’t state.
   * Does it remain unchanged over time? If so, it probably isn’t state.
   * Can you compute it based on any other state or props in your component? If so, it isn’t state.

### Identify where should state Live!

- For each piece of state in your application:

  -  Identify every component that renders something based on that state.
  - Find a common owner component (a single component above all the components that need the state in the hierarchy).
  * Either the common owner or another component higher up in the hierarchy should own the state.
  - If you can’t find a component where it makes sense to own the state, create a new component solely for holding the state and add it somewhere in the hierarchy above the common owner component.
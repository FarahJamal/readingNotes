## State and Props
What are props?
Props is short for properties and they are used to pass data between React components. React’s data flow between components is uni-directional (from parent to child only).

How do you pass data with props?
Here is an example of how data can be passed by using props:

class ParentComponent extends Component {    
    render() {    
        return (        
            <ChildComponent name="First Child" />    
        );  
    }
}

const ChildComponent = (props) => {    
    return <p>{props.name}</p>; 
};
Firstly, we need to define/get some data from the parent component and assign it to a child component’s “prop” attribute.

<ChildComponent name="First Child" />
“Name” is a defined prop here and contains text data. Then we can pass data with props like we’re giving an argument to a function:

const ChildComponent = (props) => {  
  // statements
};
And finally, we use dot notation to access the prop data and render it:

return <p>{props.name}</p>;
## Rebuilt with React?
React-Bootstrap replaces the Bootstrap JavaScript. Each component has been built from scratch as a true React component, without unneeded dependencies like jQuery.

As one of the oldest React libraries, React-Bootstrap has evolved and grown alongside React, making it an excellent choice as your UI foundation.

## Bootstrap at its core?
Built with compatibility in mind, we embrace our bootstrap core and strive to be compatible with the world’s largest UI ecosystem.

## Accessible by default?
The React component model gives us more control over form and function of each component.

Each component is implemented with accessibility in mind. The result is a set of accessible-by-default components, over what is possible from plain Bootstrap.

## What Is React?
React is a declarative, efficient, and flexible JavaScript library for building user interfaces. It lets you compose complex UIs from small and isolated pieces of code called “components”.

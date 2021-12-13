# React Cheat Sheet <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" width="40" height="40" />


Notes from Scrimba 

### Why learn React?
- It's Composable 
  - Think it as building something using lego blocks 
  - You connect blocks together to build the final product
- Building custom components 
  - maintainable
  - flexible
  
- React is declarative! 

     What? 🤔  
     <br>

Let's learn about the difference between declarative and imperative   
<br>

**> Declartive (React)**

- "Just tell me what to do and I'll figure out how to do it"
````
ReactDOM.render(<h1 className="header">Hello, React!</h1>, document.getElementById("root"))
````
<br>

**> Imperative (Vanilla JS)**

- "I need you to describe step by step how to do something and I'll do it"
````
const h1 = document.createElement("h1")
h1.textContent = "Hello, React!"
h1.className = "header"
document.getElementById("root").append(h1)
````
<br>

React is declarative and knows what we want to do just by writing jsx unlike imperative Vanilla Js. Shorter code and simple to use 👍

---

### Basic syntax of React
````
ReactDOM.render(<h1>Hello world</h1>, document.getElementById("root"))
   // rendering (html you want, where in html)
````
````
// another example 
ReactDOM.render(
  <ul><li>Hello</li><li>Hola</li></ul>, 
  document.querySelector("#root")
)
````
### How to create components

1. In js file create a function 
````
function MainContent() {
  return (
    <h1>I'm learning React!</h1>
  )
}
````
2. Call funtion in render
````
ReactDOM.render(
  <div>
    <MainContent />
  </div>,
  document.getElementById("root")
)
````
---

### Learn about JSX

JavaScript XML <br>
The html inside our JS 

What can you do? 
````
// Assign to a variable 
const element = <h1 className="header">This is JSX</h1>

// Parent and child elements into a variable
const page = (
    <div>
        <h1 className="header">This is JSX</h1>
        <p>This is a paragraph</p>
    </div>
)
````
Let's console log this `element`
````
console.log(element)

// Return JS object!
/*
{
    type: "h1", 
    key: null, 
    ref: null, 
    props: {
      className: "header", 
      children: "This is JSX"
    }, 
    _owner: null, 
    _store: {}
}
 */
 ````
 Returns objects that React can interpret and use to create actual elements that get put on the screen.   
 <br>
 Now let's call the variable in our render
 ````
ReactDOM.render(element, document.getElementById("root"))
````
<br>

⚠️ Caution

Only return a single parent element. The following will result in an error: 
````
ReactDOM.render(
    <h1 className="header">This is JSX</h1><p>This is a paragraph</p>, 
    document.getElementById("root")
)
````
Instead, create a parent element (div) and put the child elements inside the parent
````
ReactDOM.render(
    <div>
        <h1 className="header">This is JSX</h1>
        <p>This is a paragraph</p>
    </div>,
    document.getElementById("root")
)
````
<br>

Some syntax differences:
````
// className instead of class
ReactDOM.render(<h1 className="header">This is JSX</h1>, document.getElementById("root"))
````
---




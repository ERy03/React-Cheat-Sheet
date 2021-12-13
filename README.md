# React Cheat Sheet

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

Let's learn about the difference between declarative and imperative

---
Declartive (React)
- "Just tell me what to do and I'll figure out how to do it"
````
ReactDOM.render(<h1 className="header">Hello, React!</h1>, document.getElementById("root"))
````
Imperative (Vanilla JS)
- "I need you to describe step by step how to do something and I'll do it"
````
const h1 = document.createElement("h1")
h1.textContent = "Hello, React!"
h1.className = "header"
document.getElementById("root").append(h1)
````
React is declarative and knows what we want to do just by writing html unlike imperative Vanilla Js. Shorter code and simple to use 👍

---



### Basic syntax of React
````
ReactDOM.render(<h1>Hello world</h1>, document.getElementById("root"))
   # rendering (html you want, where in html)
   
# another example 
ReactDOM.render(
  <ul><li>Hello</li><li>Hola</li></ul>, 
  document.querySelector("#root")
)
````

### How to create components 
````
# 1. In js file create a function 
function MainContent() {
  return (
    <h1>I'm learning React!</h1>
  )
}

# 2. Call funtion in render
ReactDOM.render(
  <div>
    <MainContent />
  </div>,
  document.getElementById("root")
)
````

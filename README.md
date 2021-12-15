# React Cheat Sheet <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" width="40" height="40" />


Notes from Scrimba 

### Why learn React?
- It's Composable 
  - Think it as building something using lego blocks 
  - You connect small blocks together to build a page
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
```` javascript
ReactDOM.render(<h1 className="header">Hello, React!</h1>, document.getElementById("root"))
````
<br>

**> Imperative (Vanilla JS)**

- "I need you to describe step by step how to do something and I'll do it"
```` javascript
const h1 = document.createElement("h1")
h1.textContent = "Hello, React!"
h1.className = "header"
document.getElementById("root").append(h1)
````
<br>

React is declarative and knows what we want to do just by writing jsx unlike imperative Vanilla Js. Shorter code and simple to use 👍

---

### Set-up

````bash
npx create-react-app app-name
cd app-name
yarn start
````
#### Styling
1. Create a `style.css` file in the src folder
2. In index.js file `import "./style.css"`

#### Images 
1. Create a `images` folder inside src folder
2. import image and call it!
```` javascript
import reactLogo from "../images/name-of-image.png" 
// it can be any name

<img 
  src={reactLogo}
/>
````
Ensures that there are no broken images

📚 More info: https://create-react-app.dev/docs/adding-images-fonts-and-files/

---

### To do

In your index.js file:
```` javascript 
import React from 'react'
import ReactDOM from 'react-dom'
````

Why import React?     
React is what defines JSX. In other words, without React we cannot use JSX 

---

### Basic syntax of React
```` javascript
ReactDOM.render(<h1>Hello world</h1>, document.getElementById("root"))
   // rendering (html you want, where in html)
````
```` javascript
// another example 
ReactDOM.render(
  <ul><li>Hello</li><li>Hola</li></ul>, 
  document.querySelector("#root")
)
````
### How to create components

1. In js file create a function 
```` javascript
function MainContent() {
  return (
    <h1>I'm learning React!</h1>
  )
}
```` 
2. Call funtion in render
```` javascript
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
```` javascript
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
```` javascript
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
 ```` javascript
ReactDOM.render(element, document.getElementById("root"))
````
<br>

⚠️ Caution

Only return a single parent element. The following will result in an error: 
```` javascript
ReactDOM.render(
    <h1 className="header">This is JSX</h1><p>This is a paragraph</p>, 
    document.getElementById("root")
)
````
Instead, create a parent element (div) and put child elements inside the parent
```` javascript
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
```` javascript
// className instead of class
ReactDOM.render(<h1 className="header">This is JSX</h1>, document.getElementById("root"))
````
---

### Why do we use ReactDOM.render? 
we have JSX saved in a varaible called `page`
```` javascript
const page = (
    <h1>hello</h1>
)
````
what happens when we `document.getElementById("root").append(page)`?
````
[object Object]
````
Let's use `JSON.stringify(page)`
```` javascript
document.getElementById("root").append(JSON.stringify(page))

// output
{"type":"h1","key":null,"ref":null,"props":{"children":"hello"},"_owner":null,"_store":{}}
````
JSX returns plain JS objects. Has nothing to do with DOM. It's not recognized by the browser. 

That's why we need to render using `ReactDOM.render`.     
React takes this JS objects and turns them in real DOM elements that the browser can interpret. 

---

### Creating custom components 

What is a React component?              
A function that returns React elements (or UI).    

Use pascal case 
          
`function PascalCase()`

Calling React Component
```` javascript 
ReactDOM.render(<PascalCase />, document.getElementById("root"))
````
Example   
```` javascript 
import React from "react"
import ReactDOM from "react-dom"

function Page() {
    return (
        <ol>
            <li>Cool</li>
            <li>Amazing</li>
        </ol>
    )
}

ReactDOM.render(<Page />, document.getElementById("root"))
````

Parent children components    

In the example below, `Page` is the parent component and `<Header />`, `<MainContent />`, `<Footer />` are child components.

```` javascript
function Page() {              
    return (
        <div>
            <Header />         
            <MainContent />
            <Footer />
        </div>
    )
}

ReactDOM.render(<Page />, document.getElementById("root"))
````

---

### Separating components in React

1. Create a new folder called components
2. Inside of the folder, create a new file `NameOfComponent.js`
3. `import React from "react"`
4. export using one of the following:
```` javascript
// In the end
export default Header // name of function 

// When defining function
export default function Header() {
  return (
    ...
  )
}
````
5. import component in index.js      
`import Header from "/components/Header"`

---

### Tips 

1. Create a mental outline of the elements of the page    

  - What elements do you need?
  - What css layouts do you need?
  - How many components do you need?  

<img align="left" src="https://user-images.githubusercontent.com/76512208/146034956-14ccdddd-5e11-4244-87df-7e4d9b059da6.png" width="350" height="400">
<img align="right" src="https://user-images.githubusercontent.com/76512208/146035050-8c742022-8857-43a0-a20a-b90036522c6e.png" width="350" height="400">



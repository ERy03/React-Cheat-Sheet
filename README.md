# React_practice

Notes from Scrimba 

### Why learn React?
- Composable code 
- Building custom components 
  - maintainable
  - flexible


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

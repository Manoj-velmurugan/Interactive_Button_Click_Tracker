# Interactive_Button_Click_Tracker
## Date : 13/07/2025
## Objective:
To implement a counter using JavaScript closures and demonstrate how variables maintain their state across function calls, emphasizing the concepts of function scope and lexical closures.

## Tasks:

#### 1. Structure the HTML Layout:
Create a simple interface with:

A heading like ```<h1>ClickCounter</h1>```

A ```<button>``` labeled “Click Me”

A ```<p> or <div>``` to display the number of clicks

#### 2. Style with CSS:
Center the layout and apply padding and background color

Use large fonts for the click display

Add hover effects on the button

#### 3. Write JavaScript with Closure:
Create a function createCounter() that returns another function

The inner function should increment and return a count variable stored in the outer function’s scope

Use this closure to track how many times the button has been clicked

Update the DOM each time the button is clicked using the closure function
## HTML Code:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Click Counter</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="counter-container">
        <h1>Click Counter</h1>
        <button id="clickBtn">Click me</button>
        <p id="clickDisplay">Clicks : 0</p>
    </div>
    <script src="script.js"></script>
</body>
</html>
```
## CSS Code:
```
body {
  font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background: linear-gradient(to right, #f9d423, #ff4e50);
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0;
}

.counter-container {
  background-color: white;
  padding: 30px;
  border-radius: 12px;
  box-shadow: 0 6px 15px rgba(0,0,0,0.2);
  text-align: center;
}

h1 {
  color: #333;
  margin-bottom: 20px;
}

button {
  padding: 12px 20px;
  font-size: 18px;
  background-color: #28a745;
  color: white;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #218838;
}

#clickDisplay {
  margin-top: 20px;
  font-size: 22px;
  font-weight: bold;
  color: #444;
}
```
## JavaScript Code:
```
function createCounter(){
    let count = 0

    return function(){
        count++
        return count
    }
}

const counter = createCounter()

const button = document.getElementById("clickBtn")
const display = document.getElementById("clickDisplay")

button.addEventListener("click", () => {
    const clickCount = counter()
    display.textContent = `Clicks : ${clickCount}`
})
```
## Output:

## Result:
A mini module using JavaScript closure and scope is successfully implemented to build an interactive button click tracker that updates in real time without exposing internal variables.

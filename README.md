# MWAD-EXP_04-Simple-caluculator
## Date: 30.04.2025


## AIM
To  develop a Simple Calculator using React.js with clean and responsive design, ensuring a smooth user experience across different screen sizes.

## ALGORITHM
### STEP 1
Create a React App.

### STEP 2
Open a terminal and run:
  <ul><li>npx create-react-app simple-calculator</li>
  <li>cd simple-calculator</li>
  <li>npm start</li></ul>

### STEP 3
Inside the src/ folder, create a new file Calculator.js and define the basic structure.

### STEP 4
Plan the UI: Display screen, number buttons (0-9), operators (+, -, *, /), clear (C), and equal (=).

### STEP 5
Create a new file Calculator.css in src/ and add the styling.

### STEP 6
Open src/App.js and modify it.

### STEP 7
Start the development server.
  npm start

### STEP 8
Open http://localhost:3000/ in the browser.

### STEP 
Test the calculator by entering numbers and operations.

### STEP 10
Fix styling issues and refine content placement.

### STEP 11
Deploy the website.

### STEP 12
Upload to GitHub Pages for free hosting.

## PROGRAM
### App.js
```
import React, { useState } from 'react';
import './App.css';
import { evaluate } from 'mathjs';

function App() {
  const [input, setInput] = useState('');

  const handleClick = (value) => {
    if (value === 'AC') {
      setInput('');
    } else if (value === '=') {
      try {
        setInput(evaluate(input).toString());
      } catch {
        setInput('Error');
      }
    } else if (value === '+/-') {
      if (input) setInput((parseFloat(input) * -1).toString());
    } else {
      setInput((prev) => prev + value);
    }
  };

  const buttons = [
    'AC', '+/-', '%', '/',
    '7', '8', '9', '*',
    '4', '5', '6', '-',
    '1', '2', '3', '+',
    '0', '.', '='
  ];

  return (
    <div className="calculator">
      <div className="display">{input || '0'}</div>
      <div className="buttons">
        {buttons.map((btn, i) => (
          <button
            key={i}
            className={`button ${btn === '=' ? 'equal' : ''}`}
            onClick={() => handleClick(btn)}
          >
            {btn}
          </button>
        ))}
      </div>
    </div>
  );
}

export default App;

```
### App.css
```
.calculator {
  max-width: 320px;
  margin: 50px auto;
  border-radius: 20px;
  box-shadow: 0px 10px 25px rgba(0, 0, 0, 0.2);
  overflow: hidden;
  background-color: #1c1c1c;
  color: white;
  font-family: 'Arial', sans-serif;
}

.display {
  background-color: #1c1c1c;
  padding: 20px;
  font-size: 2.5em;
  text-align: right;
  color: white;
  min-height: 80px;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
}

.button {
  padding: 25px;
  font-size: 1.5em;
  border: 1px solid #333;
  background-color: #505050;
  color: white;
  cursor: pointer;
}

.button:nth-child(4n) {
  background-color: #ff9500;
  color: white;
}

.button.equal {
  background-color: #ff9500;
  color: white;
}

.button:nth-child(-n+3) {
  background-color: #d4d4d2;
  color: black;
}

.button:active {
  opacity: 0.8;
}

```

## OUTPUT
![Screenshot 2025-04-30 103807](https://github.com/user-attachments/assets/1e99e08b-2b1e-4052-bfcd-4d81685429b0)
![Screenshot 2025-04-30 103824](https://github.com/user-attachments/assets/a763c578-26ee-471b-8cc7-aff9cae01a7f)
![Screenshot 2025-04-30 103831](https://github.com/user-attachments/assets/45994a5f-89df-4a50-b9c0-3fabf29f92c1)

## RESULT
The program for developing a simple calculator in React.js is executed successfully.

<!DOCTYPE html> 
<html>
<head>
  <title>Basic Calculator</title>
  <style>
    body {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 120vh;
  margin: 0;
   font-family: Arial, sans-serif;
  background-color: #A422B8 ;
}

.calculator {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 10px;
  max-width: 350px;
  padding: 10px;
  border: 1px solid #ccc;
  background-color: #FFC300;
}

.display {
  grid-column: span 4;
  text-align: right;
  font-size: 30px;
  padding: 12px;
  background-color: #B6B2B3;
  border: 1px solid #ccc;
}

.button {
  grid-column: span 1;
  padding: 10px;
  font-size: 20px;
  text-align: center;
  cursor: pointer;
  border: 1px solid #ccc;
  background-color: #46C3BF;
}

.button:hover {
  background-color: #100401;
}

  </style>
</head>
<body>
  <div class="calculator">
    <div class="display" id="result">0</div>
    <button class="button" onclick="clearDisplay()">C</button>
    <button class="button" onclick="appendToDisplay('/')">/</button>
    <button class="button" onclick="appendToDisplay('*')">x</button>
    <button class="button" onclick="appendToDisplay('7')">7</button>
    <button class="button" onclick="appendToDisplay('8')">8</button>
    <button class="button" onclick="appendToDisplay('9')">9</button>
    <button class="button" onclick="appendToDisplay('-')">-</button>
    <button class="button" onclick="appendToDisplay('4')">4</button>
    <button class="button" onclick="appendToDisplay('5')">5</button>
    <button class="button" onclick="appendToDisplay('6')">6</button>
    <button class="button" onclick="appendToDisplay('+')">+</button>
    <button class="button" onclick="appendToDisplay('1')">1</button>
    <button class="button" onclick="appendToDisplay('2')">2</button>
    <button class="button" onclick="appendToDisplay('3')">3</button>
    <button class="button" onclick="calculate()">=</button>
    <button class="button" onclick="appendToDisplay('0')">0</button>
    <button class="button" onclick="appendToDisplay('.')">.</button>
  </div>
  <script> 
let displayValue = '0';

function updateDisplay() {
  document.getElementById('result').innerText = displayValue;
}

function clearDisplay() {
  displayValue = '0';
  updateDisplay();
}

function appendToDisplay(value) {
  if (displayValue === '0') {
    displayValue = value;
  } else {
    displayValue += value;
  }
  updateDisplay();
}

function calculate() {
  try {
    displayValue = eval(displayValue).toString();
  } catch (error) {
    displayValue = 'Error';
  }
  updateDisplay();
}

updateDisplay();

  </script>
</body>
</html>

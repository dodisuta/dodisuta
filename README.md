<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Fancy Calculator</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <div class="calculator">
    <input type="text" id="display" disabled>
    <div class="buttons">
      <button class="operator" onclick="operate('+')">+</button>
      <button class="operator" onclick="operate('-')">-</button>
      <button class="operator" onclick="operate('*')">*</button>
      <button class="operator" onclick="operate('/')">/</button>
      <button onclick="addToDisplay('7')">7</button>
      <button onclick="addToDisplay('8')">8</button>
      <button onclick="addToDisplay('9')">9</button>
      <button onclick="clearDisplay()">C</button>
      <button onclick="addToDisplay('4')">4</button>
      <button onclick="addToDisplay('5')">5</button>
      <button onclick="addToDisplay('6')">6</button>
      <button onclick="calculate()">=</button>
      <button onclick="addToDisplay('1')">1</button>
      <button onclick="addToDisplay('2')">2</button>
      <button onclick="addToDisplay('3')">3</button>
      <button onclick="addToDisplay('.')">.</button>
      <button onclick="addToDisplay('0')">0</button>
    </div>
  </div>

  <script src="script.js"></script>
</body>
</html>




let displayValue = '';

function addToDisplay(value) {
  displayValue += value;
  document.getElementById('display').value = displayValue;
}

function clearDisplay() {
  displayValue = '';
  document.getElementById('display').value = displayValue;
}

function operate(operator) {
  displayValue += operator;
  document.getElementById('display').value = displayValue;
}

function calculate() {
  try {
    const result = eval(displayValue);
    displayValue = String(result);
    document.getElementById('display').value = displayValue;
  } catch (error) {
    displayValue = '';
    document.getElementById('display').value = 'Error';
  }
}



body {
  display: flex;
  justify-content: center;
  align-items:center;
  height: 100vh;
  margin: 0;
  font-family: Arial, sans-serif;
  background-color: #f5f5f5;
}

.calculator {
  background-color: #fff;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  padding: 20px;
  max-width: 300px;
  width: 100%;
}

#display {
  width: calc(100% - 10px);
  margin-bottom: 10px;
  padding: 10px;
  border: none;
  border-radius: 5px;
  font-size: 1.5em;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}

button {
  padding: 15px;
  font-size: 1.2em;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #e0e0e0;
}

.operator {
  background-color: #fca311;
  color: #fff;
}


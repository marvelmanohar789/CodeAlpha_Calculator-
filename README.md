# CodeAlpha_Calculator-
Responsive Calculator built using HTML, CSS and JavaScript.

calculator.html code :
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator</title>

    <link rel="stylesheet" href="calculator.css">
</head>
<body>

    <div class="calculator">

        <input type="text" id="display" disabled>

        <div class="buttons">

            <button onclick="clearDisplay()">C</button>
            <button onclick="deleteLast()">DEL</button>
            <button onclick="appendValue('%')">%</button>
            <button onclick="appendValue('/')">/</button>

            <button onclick="appendValue('7')">7</button>
            <button onclick="appendValue('8')">8</button>
            <button onclick="appendValue('9')">9</button>
            <button onclick="appendValue('*')">*</button>

            <button onclick="appendValue('4')">4</button>
            <button onclick="appendValue('5')">5</button>
            <button onclick="appendValue('6')">6</button>
            <button onclick="appendValue('-')">-</button>

            <button onclick="appendValue('1')">1</button>
            <button onclick="appendValue('2')">2</button>
            <button onclick="appendValue('3')">3</button>
            <button onclick="appendValue('+')">+</button>

            <button onclick="appendValue('0')">0</button>
            <button onclick="appendValue('.')">.</button>
            <button onclick="calculate()">=</button>

        </div>
    </div>

    <script src="calculator.js"></script>

</body>
</html>



calculator.css code:

body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background: #fcfcfc;
    font-family: Arial;
}

.calculator {
    background: rgb(31, 29, 29);
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 0 10px gray;
}

#display {
    width: 100%;
    height: 50px;
    margin-bottom: 10px;
    font-size: 24px;
    text-align: right;
    padding-right: 10px;
}

.buttons {
    display: grid;
    grid-template-columns: repeat(4, 70px);
    gap: 10px;
}

button {
    height: 60px;
    font-size: 20px;
    border: none;
    background: #3498db;
    color: white;
    border-radius: 8px;
    cursor: pointer;
}

button:hover {
    background: #04315f;
}




calculator.js code:

let display = document.getElementById("display");

function appendValue(value) {
    display.value += value;
}

function clearDisplay() {
    display.value = "";
}

function deleteLast() {
    display.value = display.value.slice(0, -1);
}

function calculate() {
    try {
        display.value = eval(display.value);
    } catch {
        display.value = "Error";
    }
}

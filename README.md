
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Calculator</title>
    
    <style>
        /* CSS: Styling the Calculator */
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #f6f5f5; 
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

        .calculator {
            background-color: #1e1e1e;
            padding: 20px;
            border-radius: 20px;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.5);
            width: 320px;
        }

        #display {
            width: 100%;
            height: 70px;
            background-color: #2c2c2c;
            border: none;
            border-radius: 10px;
            color: #ffffff;
            font-size: 2.5rem;
            text-align: right;
            padding: 10px;
            box-sizing: border-box; 
            margin-bottom: 20px;
        }

        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr); 
            gap: 12px;
        }

        button {
            background-color: #333333;
            color: white;
            border: none;
            padding: 20px;
            font-size: 1.2rem;
            border-radius: 12px;
            cursor: pointer;
            transition: background-color 0.2s, transform 0.1s;
        }

        button:hover {
            background-color: #444444;
        }

        button:active {
            transform: scale(0.95);
        }

        
        .operator {
            background-color: #ff9f0a;
            color: white;
            font-weight: bold;
        }

        .operator:hover {
            background-color: #ffb03b;
        }

        /* Equals button styling */
        .equals {
            background-color: #34c759; 
            grid-column: span 2; 
        }
        
        .equals:hover {
            background-color: #4add72;
        }

        
        .action-btn {
            background-color: #a5a5a5;
            color: black;
        }
        
        .action-btn:hover {
            background-color: #d4d4d4;
        }

    </style>
</head>
<body>
    
  
    <div class="calculator">
        <input type="text" id="display" readonly>

        <div class="buttons">
            <button class="action-btn" onclick="clearDisplay()">AC</button>
            <button class="action-btn" onclick="deleteLast()">DEL</button>
            <button class="operator" onclick="appendValue('%')">%</button>
            <button class="operator" onclick="appendValue('/')">/</button>

            <button onclick="appendValue('7')">7</button>
            <button onclick="appendValue('8')">8</button>
            <button onclick="appendValue('9')">9</button>
            <button class="operator" onclick="appendValue('*')">×</button>

            <button onclick="appendValue('4')">4</button>
            <button onclick="appendValue('5')">5</button>
            <button onclick="appendValue('6')">6</button>
            <button class="operator" onclick="appendValue('-')">−</button>

            <button onclick="appendValue('1')">1</button>
            <button onclick="appendValue('2')">2</button>
            <button onclick="appendValue('3')">3</button>
            <button class="operator" onclick="appendValue('+')">+</button>

            <button onclick="appendValue('0')">0</button>
            <button onclick="appendValue('.')">.</button>
            <button class="equals" onclick="calculate()">=</button>
        </div>
    </div>

    <script>
        

        const display = document.getElementById('display');

    
        function appendValue(input) {
            display.value += input;
        }

        
        function clearDisplay() {
            display.value = "";
        }

        
        function deleteLast() {
            display.value = display.value.toString().slice(0, -1);
        }

        
        function calculate() {
            try {
                
        
                if (display.value === "") return;
                
        
                
                display.value = eval(display.value);
            } catch (error) {
                display.value = "Error";
                setTimeout(() => clearDisplay(), 1500); 
            }
        }
    </script>
</body>
</html>

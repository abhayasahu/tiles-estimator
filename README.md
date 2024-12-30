<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tiles Estimator</title>
  
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f9;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .container {
            background-color: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            width: 300px;
        }

        h1 {
            text-align: center;
            color: #333;
        }

        label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
        }

        input, select {
            width: 100%;
            padding: 8px;
            margin-bottom: 15px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        button {
            width: 100%;
            padding: 10px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        button:hover {
            background-color: #45a049;
        }

        h2 {
            text-align: center;
            color: #333;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Tiles Estimator</h1>
        
        <label for="length">Wall / Floor Length (in feet):</label>
        <input type="number" id="length" placeholder="Enter length in feet" />

        <label for="height">Wall / Floor Height (in feet):</label>
        <input type="number" id="height" placeholder="Enter height in feet" />

        <label for="size">Select Size:</label>
        <select id="size">
            <option value="0.66">12" x 8"</option>
            <option value="1.04">10" x 15"</option>
            <option value="1">12" x 12"</option>
            <option value="1.5">12" x 18"</option>
            <option value="3">18" x 24"</option>
            <option value="4">24" x 24"</option>
            <option value="8">24" x 48"</option>
        </select>

        <button onclick="calculate()">Calculate</button>

        <h2>Your Total Area: <span id="result">0</span> sqft</h2>
        <h2>Nos of Tiles: <span id="result1">0</span> Pcs</h2>
    </div>

    <script>
        function calculate() {
            const length = parseFloat(document.getElementById("length").value);
            const height = parseFloat(document.getElementById("height").value);
            const size = parseFloat(document.getElementById("size").value);
            
            if (isNaN(length) || isNaN(height) || length <= 0 || height <= 0) {
                alert("Please enter valid positive numbers for length and height.");
                return;
            }
            
            const result = length * height;
            const result1 = result / size;

            document.getElementById("result").textContent = result.toFixed(2);
            document.getElementById("result1").textContent = result1.toFixed(2);
        }
    </script>
</body>
</html>

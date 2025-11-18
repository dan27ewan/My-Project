<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Calculator</title>

<style>
  body {
    background: url("background.jpg") center/cover no-repeat;
    font-family: Arial, sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
  }

  .calculator {
    background: rgba(0,0,0,0.75);
    padding: 20px;
    border-radius: 12px;
    width: 260px;
  }

  #display {
    width: 90%;
    height: 50px;
    font-size: 22px;
    margin-bottom: 10px;
    padding: 10px;
    border-radius: 6px;
    border: none;
    color:white;
  }

  .buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr); 
    gap: 8px;
  }

  .buttons button {
    height: 55px;
    border: none;
    border-radius: 8px;
    font-size: 20px;
    cursor: pointer;
    background: #444;
    color: #fff;
  }

  .buttons button:hover {
    background: #666;
  }

  #twistImage {
    width: 100%;
    margin-top: 10px;
    display: none;
    border-radius: 8px;
  }
</style>
</head>

<body>

<div class="calculator">
  <input type="text" id="display" disabled>

  <div class="buttons">
    
    <button onclick="add('1')">1</button>
    <button onclick="add('2')">2</button>
    <button onclick="add('3')">3</button>
    <button onclick="add('+')">+</button>

    <button onclick="add('4')">4</button>
    <button onclick="add('5')">5</button>
    <button onclick="add('6')">6</button>
    <button onclick="add('-')">−</button>

    <button onclick="add('7')">7</button>
    <button onclick="add('8')">8</button>
    <button onclick="add('9')">9</button>
    <button onclick="add('*')">×</button>

    <button onclick="clearDisplay()">C</button>
    <button onclick="add('0')">0</button>
    <button onclick="calculate()">=</button>
    <button onclick="add('/')">÷</button>
  </div>

  <img id="twistImage">
</div>

<script>
function add(value) {
  document.getElementById('display').value += value;
}

function clearDisplay() {
  document.getElementById('display').value = "";
  document.getElementById('twistImage').style.display = "none";
}

function calculate() {
  const display = document.getElementById('display');
  const twistImage = document.getElementById('twistImage');

  try {
    display.value = eval(display.value);
  } catch {
    display.value = "Error";
  }

  const images = ["a.jpg","b.jpg","c.jpg","d.jpg","e.jpg","ewan.jpg"];

  const randomImage = images[Math.floor(Math.random() * images.length)];

  twistImage.src = randomImage;
  twistImage.style.display = "block";
}
</script>

</body>
</html>

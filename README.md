
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Calculatrice Animée</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: linear-gradient(135deg, #4facfe, #00f2fe);
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }
    .container {
      background: white;
      padding: 20px;
      border-radius: 15px;
      box-shadow: 0 8px 20px rgba(0,0,0,0.2);
      width: 90%;
      max-width: 400px;
    }
    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
    }
    button {
      padding: 15px;
      font-size: 18px;
      border-radius: 10px;
      border: none;
      background: #4facfe;
      color: white;
      transition: 0.3s;
    }
    button:hover {
      background: #00f2fe;
      transform: scale(1.05);
    }
    #display {
      width: 100%;
      padding: 15px;
      font-size: 20px;
      margin-bottom: 10px;
      border-radius: 10px;
      border: 1px solid #ccc;
      text-align: right;
    }
    .game {
      margin-top: 20px;
      text-align: center;
    }
  </style>
</head>
<body>
  <div class="container">
    <h2>✨ Calculatrice Animée ✨</h2>
    <input type="text" id="display" disabled>
    <div class="buttons">
      <button onclick="press('7')">7</button>
      <button onclick="press('8')">8</button>
      <button onclick="press('9')">9</button>
      <button onclick="press('/')">÷</button>
      <button onclick="press('4')">4</button>
      <button onclick="press('5')">5</button>
      <button onclick="press('6')">6</button>
      <button onclick="press('*')">×</button>
      <button onclick="press('1')">1</button>
      <button onclick="press('2')">2</button>
      <button onclick="press('3')">3</button>
      <button onclick="press('-')">−</button>
      <button onclick="press('0')">0</button>
      <button onclick="press('.')">.</button>
      <button onclick="calculate()">=</button>
      <button onclick="press('+')">+</button>
      <button onclick="clearDisplay()">C</button>
    </div>

    <div class="game">
      <h3>Mini-jeu 🎮</h3>
      <button onclick="play()">Clique-moi !</button>
      <p id="score">Score : 0</p>
    </div>
  </div>

  <script>
    let display = document.getElementById("display");
    function press(val) {
      display.value += val;
    }
    function calculate() {
      try {
        display.value = eval(display.value);
      } catch {
        display.value = "Erreur";
      }
    }
    function clearDisplay() {
      display.value = "";
    }

    // Mini-jeu
    let score = 0;
    function play() {
      score++;
      document.getElementById("score").innerText = "Score : " + score;
    }
  </script>
</body>
</html>

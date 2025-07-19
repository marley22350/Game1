# Game1
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Slot 6x6 Simulasi</title>
  <style>
    body {
      background: #000;
      color: #fff;
      font-family: sans-serif;
      text-align: center;
      padding: 20px;
    }
    .grid {
      display: grid;
      grid-template-columns: repeat(6, 60px);
      grid-gap: 10px;
      justify-content: center;
      margin-bottom: 20px;
    }
    .cell {
      width: 60px;
      height: 60px;
      background: #222;
      border: 2px solid #555;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 20px;
    }
    .win-message {
      color: #ff0000;
      font-size: 24px;
      margin-top: 20px;
      display: none;
    }
    button {
      padding: 10px 20px;
      font-size: 18px;
      border: none;
      background: #ffd700;
      color: #000;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <h2>💸 Slot 6x6 Simulasi</h2>
  <div class="grid" id="slotGrid"></div>
  <button onclick="spin()">Putar Slot</button>
  <div class="win-message" id="winMessage">Tolong jangan menang 😭</div>

  <script>
    function randomSymbol() {
      const symbols = ['🍒','🍋','🔔','⭐','💎','🍀'];
      return symbols[Math.floor(Math.random() * symbols.length)];
    }

    function spin() {
      const grid = document.getElementById("slotGrid");
      grid.innerHTML = "";
      for (let i = 0; i < 36; i++) {
        const cell = document.createElement("div");
        cell.className = "cell";
        cell.textContent = randomSymbol();
        grid.appendChild(cell);
      }

      // Simulasi "kalah"
      document.getElementById("winMessage").style.display = "block";
      setTimeout(() => {
        document.getElementById("winMessage").style.display = "none";
      }, 2000);
    }

    spin(); // spin saat pertama dibuka
  </script>
</body>
</html>

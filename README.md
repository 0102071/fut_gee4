<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Futebol de Botão</title>
  <style>
    html, body {
      margin: 0;
      padding: 0;
      background: #008000;
      overflow: hidden;
      font-family: sans-serif;
    }
    #manual {
      position: absolute;
      top: 10%;
      left: 10%;
      width: 80%;
      height: 80%;
      background: white;
      color: black;
      padding: 20px;
      box-shadow: 0 0 10px black;
      overflow-y: auto;
      z-index: 10;
    }
    #start {
      margin-top: 20px;
      padding: 10px;
      background-color: green;
      color: white;
      border: none;
      font-size: 16px;
      cursor: pointer;
    }
    canvas {
      display: block;
    }
  </style>
</head>
<body>
<div id="manual">
  <h1>Manual de Jogo - Futebol de Botão</h1>
  <p><strong>Movimentos:</strong></p>
  <ul>
    <li>Seta Direita: mover para a direita</li>
    <li>Seta Esquerda: mover para a esquerda</li>
    <li>Seta Cima: mover para o campo adversário</li>
    <li>Seta Baixo: mover para seu campo</li>
    <li>Espaço: chute/passe</li>
  </ul>
  <p><strong>Objetivo:</strong> Marque 5 gols ou seja o time com mais gols em 5 minutos.</p>
  <p><strong>Times:</strong> Você é o Brasil (Amarelo). O oponente será um país aleatório.</p>
  <p><strong>Início:</strong> Escolha a dificuldade após fechar este manual.</p>
  <button id="start">Fechar e Começar</button>
</div>
<canvas id="gameCanvas" width="1000" height="600"></canvas>
<script>
  const manual = document.getElementById('manual');
  const startBtn = document.getElementById('start');
  const canvas = document.getElementById('gameCanvas');
  const ctx = canvas.getContext('2d');
  let gameStarted = false;

  startBtn.onclick = () => {
    manual.style.display = 'none';
    chooseDifficulty();
  }

  function chooseDifficulty() {
    const difficulty = prompt("Escolha a dificuldade: facil, medio, dificil, muito dificil").toLowerCase();
    if (!["facil", "medio", "dificil", "muito dificil"].includes(difficulty)) {
      alert("Dificuldade inválida, escolha novamente.");
      chooseDifficulty();
    } else {
      startGame(difficulty);
    }
  }

  function startGame(difficulty) {
    // Função placeholder: aqui vai o código do jogo completo
    ctx.fillStyle = "#006400";
    ctx.fillRect(0, 0, canvas.width, canvas.height);
    ctx.fillStyle = "white";
    ctx.fillRect(canvas.width / 2 - 2, 0, 4, canvas.height); // Linha do meio
    ctx.fillText("Carregando jogo: " + difficulty, 400, 300);
    // Aqui você inserirá a lógica do jogo semelhante ao Haxball
  }
</script>
</body>
</html>

# Click-game-
Jogo simples de clicar em um alvo para ganhar pontos, criado em HTML5 e JavaScript. Pode ser usado para aprender desenvolvimento web ou se divertir.
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8" />
<title>Jogo de Clique para Pontuar</title>
<style>
  body { font-family: Arial, sans-serif; text-align: center; padding: 40px; }
  #gameArea { margin: 20px auto; width: 400px; height: 400px; border: 2px solid #333; position: relative; }
  #target { width: 50px; height: 50px; background-color: red; border-radius: 50%; position: absolute; cursor: pointer; }
  #score { font-size: 24px; }
</style>
</head>
<body>
<h1>Jogo de Clique</h1>
<div id="score">Pontuação: 0</div>
<div id="gameArea">
  <div id="target"></div>
</div>

<script>
  let score = 0;
  const target = document.getElementById('target');
  const gameArea = document.getElementById('gameArea');
  const scoreDisplay = document.getElementById('score');

  function moveTarget() {
    const maxX = gameArea.clientWidth - target.clientWidth;
    const maxY = gameArea.clientHeight - target.clientHeight;
    const randomX = Math.floor(Math.random() * maxX);
    const randomY = Math.floor(Math.random() * maxY);
    target.style.left = randomX + 'px';
    target.style.top = randomY + 'px';
  }

  target.addEventListener('click', () => {
    score += 1;
    scoreDisplay.textContent = 'Pontuação: ' + score;
    moveTarget();
  });

  // Inicializa o alvo numa posição aleatória
  moveTarget();
</script>
</body>
</html>

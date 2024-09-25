
<html lang="en">
<head>

  <title>demo game</title>
  <style>
    body {
      margin: 0;
      padding: 10;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background-color: #095496;
      font-family: Arial, sans-serif;
    }

    .game-container {
      position: relative;
      width: 650px;
      height: 450px;
      border: 2px solid #70ef4a5c;
      background-color: #e8be72;
    }

    .box {
      position: absolute;
      width: 40px;
      height: 70px;
      background-color: #717070;
      cursor: pointer;
    }

    .score {
      position: absolute;
      top: 10px;
      left: 10px;
      font-size: 20px;
      color: #000;
    }
  </style>
</head>
<body>

  <div class="game-container">
    <div class="score" id="score">Score: 0</div>
    <div class="box" id="box"></div>
  </div>
   --its a demo game
  <script>
    let score = 0;
    const box = document.getElementById('box');
    const scoreDisplay = document.getElementById('score');
    const gameContainer = document.querySelector('.game-container');

    function moveBox() {
      const containerWidth = gameContainer.clientWidth;
      const containerHeight = gameContainer.clientHeight;
      const boxSize = 50;
      
      // Random position within the container boundaries
      const randomX = Math.random() * (containerWidth - boxSize);
      const randomY = Math.random() * (containerHeight - boxSize);
      
      box.style.left = `${randomX}px`;
      box.style.top = `${randomY}px`;

    }

    box.addEventListener('click', () => {
      score++;
      scoreDisplay.textContent = `Score: ${score}`;
      moveBox();
    });

    moveBox();
  </script>

</body>
</html>

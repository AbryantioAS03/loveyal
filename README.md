<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Kumpulin Hati - Agam for Al</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: 'Arial', sans-serif;
      background: linear-gradient(135deg, #a3d8f4, #f4a3c4);
      overflow: hidden;
    }
    h1 {
      text-align: center;
      color: white;
      margin-top: 20px;
      font-size: 2rem;
    }
    .game-container {
      position: relative;
      width: 100vw;
      height: 90vh;
    }
    .heart {
      width: 40px;
      height: 40px;
      background: url('https://upload.wikimedia.org/wikipedia/commons/2/2f/Heart_icon_red_hollow.svg') no-repeat center/contain;
      position: absolute;
      cursor: pointer;
      animation: float 5s linear infinite;
    }
    @keyframes float {
      0% {
        transform: translateY(100vh);
      }
      100% {
        transform: translateY(-10vh);
      }
    }
    #message {
      display: none;
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      background-color: rgba(255, 255, 255, 0.9);
      padding: 30px;
      border-radius: 15px;
      box-shadow: 0 0 10px rgba(0,0,0,0.3);
      font-size: 1.2rem;
      text-align: center;
      max-width: 80%;
    }
    #message strong {
      color: #e91e63;
    }
  </style>
</head>
<body>
  <h1>Kumpulin Hati untuk Al 💖</h1>
  <div class="game-container" id="game-container"></div>
  <div id="message">
   <p><strong>Meeting you was the best twist of fate in my life.</strong><br>
    I didn’t expect it, but I’m so endlessly grateful.</p>
    <p>— Agam</p>
  </div>
  <audio id="bg-music" autoplay loop>
    <source src="https://dl.dropboxusercontent.com/scl/fi/w4cuxmh4bw8x0h1s3w6oy/pocket-locket.mp3?rlkey=fugurq8uj3a5o12dv07kds86f&st=0gssjtx7&dl=0" type="audio/mpeg">
  </audio>
  <script>
    const gameContainer = document.getElementById("game-container");
    const message = document.getElementById("message");
    let heartsCollected = 0;function createHeart() {
  const heart = document.createElement("div");
  heart.classList.add("heart");
  heart.style.left = Math.random() * 90 + "vw";
  heart.style.top = Math.random() * 80 + 10 + "vh";

  heart.addEventListener("click", () => {
    heart.remove();
    heartsCollected++;
    if (heartsCollected >= 5) {
      message.style.display = "block";
    }
  });

  gameContainer.appendChild(heart);
  setTimeout(() => {
    heart.remove();
  }, 6000);
}

setInterval(createHeart, 1000);

  </script>
</body>
</html>

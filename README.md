<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>For You, Always</title>

  <style>
    body {
      margin: 0;
      height: 100vh;
      background: linear-gradient(135deg, #f6c1cc, #fbe3e8);
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: 'Georgia', serif;
      color: #6a2c39;
      overflow: hidden;
    }

    .card {
      background: rgba(255, 255, 255, 0.6);
      padding: 45px 35px;
      border-radius: 30px;
      max-width: 420px;
      text-align: center;
      box-shadow: 0 15px 35px rgba(0,0,0,0.12);
      animation: fadeIn 2s ease;
      z-index: 2;
    }

    h1 {
      font-size: 2.1em;
      margin-bottom: 15px;
    }

    p {
      font-size: 1.15em;
      line-height: 1.6;
      opacity: 0;
      animation: fadeIn 2s ease forwards;
      animation-delay: 1s;
    }

    button {
      margin-top: 28px;
      padding: 14px 32px;
      font-size: 17px;
      border: none;
      border-radius: 30px;
      background: #c94b62;
      color: #fff;
      cursor: pointer;
      transition: transform 0.2s, box-shadow 0.2s;
      box-shadow: 0 6px 15px rgba(201,75,98,0.4);
    }

    button:hover {
      transform: translateY(-2px);
      box-shadow: 0 10px 20px rgba(201,75,98,0.5);
    }

    .hidden {
      display: none;
    }

    #secret {
      margin-top: 25px;
      animation: fadeIn 2s ease forwards;
    }

    /* Floating hearts */
    .heart {
      position: absolute;
      bottom: -20px;
      font-size: 20px;
      color: rgba(201, 75, 98, 0.6);
      animation: floatUp 8s linear infinite;
    }

    @keyframes floatUp {
      0% {
        transform: translateY(0);
        opacity: 0;
      }
      10% {
        opacity: 1;
      }
      100% {
        transform: translateY(-110vh);
        opacity: 0;
      }
    }

    @keyframes fadeIn {
      from {
        opacity: 0;
        transform: translateY(10px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }
  </style>
</head>

<body>

  <div class="card">
    <h1>Happy Valentine’s Day, my love</h1>

    <p id="intro">
      Loving you feels calm, warm, and right—  
      like coming home every time I see you.
    </p>

    <button onclick="reveal()">Open my heart 💌</button>

    <p id="secret" class="hidden">
      You are my favorite place to be.  
      My safest feeling.  
      My always.  
      <br><br>
      Will you be my Valentine?
    </p>
  </div>

  <!-- Background music (replace link if you want) -->
  <audio id="music" loop>
    <source src="https://cdn.pixabay.com/audio/2022/10/26/audio_9c4b6a2f9b.mp3" type="audio/mpeg">
  </audio>

  <script>
    function reveal() {
      document.getElementById("secret").classList.remove("hidden");
      document.getElementById("music").play();
    }

    // Create floating hearts
    setInterval(() => {
      const heart = document.createElement("div");
      heart.className = "heart";
      heart.innerHTML = "❤";
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.animationDuration = (6 + Math.random() * 4) + "s";
      document.body.appendChild(heart);

      setTimeout(() => {
        heart.remove();
      }, 10000);
    }, 600);
  </script>

</body>
</html>

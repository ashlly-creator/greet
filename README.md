<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Happy Birthday Ate!</title>
  <style>
    /* 🌸 General Page Style */
    body {
      margin: 0;
      height: 100vh;
      background: linear-gradient(135deg, #ffd1dc, #b3e5fc);
      overflow: hidden;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      font-family: "Pacifico", sans-serif;
      text-align: center;
    }

    h1 {
      font-size: 2.5em;
      color: #ff4081;
      margin-bottom: 10px;
      text-shadow: 2px 2px 5px rgba(0,0,0,0.2);
      animation: pop 1s ease-in-out;
      padding: 0 10px;
    }

    p {
      font-size: 1.1em;
      color: #333;
      width: 90%;
      max-width: 600px;
      line-height: 1.5;
      padding: 0 10px;
    }

    img {
      width: 230px;
      border-radius: 15px;
      margin-top: 20px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
      animation: bounce 2s infinite ease-in-out;
    }

    /* 🌈 Floating Balloons */
    .balloon {
      position: absolute;
      bottom: -150px;
      width: 50px;
      height: 70px;
      border-radius: 50%;
      background: red;
      animation: float 6s linear infinite;
      opacity: 0.8;
    }

    .balloon::after {
      content: '';
      position: absolute;
      width: 2px;
      height: 40px;
      background: #555;
      left: 50%;
      bottom: -40px;
      transform: translateX(-50%);
    }

    @keyframes float {
      0% { transform: translateY(0) rotate(0deg); }
      100% { transform: translateY(-120vh) rotate(360deg); }
    }

    /* 💖 Pop animation for text */
    @keyframes pop {
      0% { transform: scale(0.5); opacity: 0; }
      100% { transform: scale(1); opacity: 1; }
    }

    /* 🐶 Bounce for image */
    @keyframes bounce {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-10px); }
    }

    /* 🎊 Confetti */
    .confetti {
      position: absolute;
      width: 8px;
      height: 8px;
      background: gold;
      top: -10px;
      animation: fall 4s linear infinite;
    }

    @keyframes fall {
      0% { transform: translateY(0) rotate(0); opacity: 1; }
      100% { transform: translateY(100vh) rotate(360deg); opacity: 0; }
    }

    /* 🎵 Music Button */
    #musicBtn {
      background: #ff80ab;
      color: white;
      border: none;
      padding: 12px 25px;
      border-radius: 30px;
      font-size: 1em;
      cursor: pointer;
      margin-top: 20px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
      transition: 0.3s;
    }

    #musicBtn:hover {
      background: #f06292;
      transform: scale(1.05);
    }

    @media (max-width: 600px) {
      h1 { font-size: 2em; }
      img { width: 200px; }
      p { font-size: 1em; }
    }
  </style>
</head>
<body>
  <h1>🎉 HAPPY BIRTHDAY ATE!!!! 🎂</h1>
  <p>
    Thank you for all the sacrifices and everything you’ve done for us. I really appreciate it, even if I don’t always say it or show it. In my mind, I’m always thankful for everything you’ve given and done.

You’re a great sister to me and to Miggy — may his soul rest in peace. I know he’s also thankful for you, especially for taking care of Mami.

Mami loves you, I love you, Miggy loves you, Mama loves you, and all of us love you because we’re family.

Always take care, Ate. I know life is hard, but keep on going and never give up on your goals and your life. I know someday you’ll get everything you want — just be patient.
  </p>

  <img src="https://i.pinimg.com/474x/e6/9d/35/e69d35799c11bb96e13dff2eb6451bda.jpg" alt="Smiling Dog Meme">

  <p>Thank you for always being there for us. HAVE A NICE DAY! LABYU!!!! 💕<br><small>- From Ashlly</small></p>

  <!-- 🎵 Background Music -->
  <audio id="bgMusic" loop>
    <source src="happy-birthday-220024 (1).mp3" type="audio/mpeg">
  </audio>

  <button id="musicBtn" style="display:none;">🎵 Play Music</button>

  <script>
    const bgMusic = document.getElementById("bgMusic");
    const musicBtn = document.getElementById("musicBtn");

    // Try autoplay
    bgMusic.play().catch(() => {
      // Show button if autoplay fails
      musicBtn.style.display = "block";
    });

    // Play music when user clicks
    musicBtn.addEventListener("click", () => {
      bgMusic.play();
      musicBtn.style.display = "none";
    });

    // 🎈 Create Floating Balloons
    const colors = ['#ff4081', '#81d4fa', '#ffeb3b', '#a5d6a7', '#f48fb1'];
    for (let i = 0; i < 10; i++) {
      const balloon = document.createElement('div');
      balloon.classList.add('balloon');
      balloon.style.left = Math.random() * 100 + 'vw';
      balloon.style.background = colors[Math.floor(Math.random() * colors.length)];
      balloon.style.animationDuration = (4 + Math.random() * 4) + 's';
      document.body.appendChild(balloon);
    }

    // 🎊 Create Confetti
    for (let i = 0; i < 100; i++) {
      const confetti = document.createElement('div');
      confetti.classList.add('confetti');
      confetti.style.left = Math.random() * 100 + 'vw';
      confetti.style.background = colors[Math.floor(Math.random() * colors.length)];
      confetti.style.animationDuration = (2 + Math.random() * 3) + 's';
      confetti.style.animationDelay = Math.random() * 3 + 's';
      document.body.appendChild(confetti);
    }
  </script>
</body>
</html>

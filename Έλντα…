<!DOCTYPE html>
<html lang="el">
<head>
  <meta charset="UTF-8">
  <title>Έλντα μου 💖</title>
  <style>
    body {
      font-family: "Georgia", serif;
      background: radial-gradient(circle at top, #ffe6f0, #fff);
      text-align: center;
      padding-top: 80px;
      overflow: hidden;
      color: #b30059;
    }

    h1 {
      font-size: 42px;
      margin-bottom: 15px;
    }

    p {
      font-size: 24px;
      margin-bottom: 40px;
    }

    button {
      font-size: 26px;
      padding: 18px 40px;
      margin: 12px;
      cursor: pointer;
      border-radius: 50px;
      border: none;
      transition: all 0.4s ease;
    }

    #yes {
      background: linear-gradient(135deg, #ff4d88, #ff80aa);
      color: white;
      box-shadow: 0 15px 30px rgba(255,77,136,0.5);
    }

    #no {
      background: #f7c7d9;
      color: #b30059;
    }

    .heart {
      position: fixed;
      color: #ff4d88;
      animation: floatUp 5s ease-in forwards;
      pointer-events: none;
    }

    @keyframes floatUp {
      from {
        bottom: -10px;
        opacity: 0;
        transform: translateX(0) scale(0.8);
      }
      to {
        bottom: 110vh;
        opacity: 1;
        transform: translateX(40px) scale(1.4);
      }
    }
  </style>
</head>
<body>

  <h1 id="title">Έλντα μου 💖</h1>
  <p id="text">Θέλεις να γίνεις η Βαλεντίνα μου;</p>

  <button id="yes">Ναι</button>
  <button id="no">Όχι</button>

  <!-- Μουσική με preload -->
  <audio id="music" src="https://cdn.pixabay.com/download/audio/2022/03/15/audio_7c8c6c7e0c.mp3" preload="auto"></audio>

  <script>
    let yesStage = 0;
    let noStage = 0;
    let musicStarted = false; // για να ξεκινήσει ΜΟΝΟ μία φορά

    const yesBtn = document.getElementById("yes");
    const noBtn = document.getElementById("no");
    const text = document.getElementById("text");
    const title = document.getElementById("title");
    const music = document.getElementById("music");

    function createHeart() {
      const heart = document.createElement("div");
      heart.className = "heart";
      heart.innerHTML = Math.random() > 0.5 ? "💖" : "💗";
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.fontSize = (22 + Math.random() * 30) + "px";
      document.body.appendChild(heart);
      setTimeout(() => heart.remove(), 5000);
    }

    function heartRain() {
      for (let i = 0; i < 5; i++) {
        setTimeout(createHeart, i * 150);
      }
    }

    yesBtn.onclick = () => {
      // Ξεκινάει η μουσική ΜΟΝΟ μια φορά
      if (!musicStarted) {
        music.play().catch(e => console.log("Μουσική δεν παίχτηκε αυτόματα, αλλά θα ξεκινήσει με κλικ."));
        musicStarted = true;
      }

      heartRain();
      setInterval(heartRain, 1200);

      if (yesStage === 0) {
        text.innerText = "Είσαι σίγουρη, Έλντα μου, πως θέλεις εμένα; 💕";
        yesBtn.innerText = "Είμαι σίγουρη";
        yesStage = 1;
      } else {
        title.innerText = "💘 Έλντα μου 💘";
        text.innerText = "Σε διάλεξα, Έλντα μου. Και θα σε διάλεγα ξανά και ξανά, χωρίς δεύτερη σκέψη. 💖";
        yesBtn.style.display = "none";
        noBtn.style.display = "none";
      }
    };

    noBtn.onclick = () => {
      noStage++;
      yesBtn.style.transform = "scale(" + (1 + noStage * 0.18) + ")";

      if (noStage === 1) {
        text.innerText = "Σκέψου το λίγο ακόμα, Έλντα μου… 💭";
      } else if (noStage === 2) {
        text.innerText = "Υπόσχομαι χαμόγελα, αγκαλιές και φροντίδα 💗";
      } else if (noStage === 3) {
        text.innerText = "Θα είμαι εδώ, στα εύκολα και στα δύσκολα 🫶";
      } else if (noStage === 4) {
        text.innerText = "Δεν ψάχνω κάτι τέλειο. Ψάχνω εσένα, Έλντα μου 💖";
      } else {
        text.innerText = "Νομίζω πως η καρδιά σου ήδη ξέρει την απάντηση, Έλντα μου 💘";
        noBtn.style.display = "none";
      }
    };
  </script>

</body>
</html>

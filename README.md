<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Romantic Love Page</title>
  <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@500;700&family=Poppins:wght@300;500;700&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      padding: 0;
      height: 100vh;
      overflow: hidden;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      background: linear-gradient(to bottom right, #ffe6eb, #ffd6e0);
      font-family: 'Poppins', sans-serif;
      text-align: center;
    }

    h1 {
      color: #e91e63;
      font-family: 'Dancing Script', cursive;
      font-size: 2.8em;
      margin-bottom: 20px;
      animation: fadeIn 2s ease-in-out;
    }

    button {
      background-color: #ff80ab;
      border: none;
      color: white;
      font-size: 1.2em;
      padding: 12px 25px;
      border-radius: 25px;
      cursor: pointer;
      box-shadow: 0 4px 10px rgba(255, 128, 171, 0.5);
      transition: transform 0.2s, background-color 0.3s;
    }

    button:hover {
      background-color: #ec407a;
      transform: scale(1.05);
    }

    /* Hati jatuh */
    .heart {
      position: fixed;
      top: -10px;
      color: #ff4d79;
      font-size: 18px;
      animation: fall linear forwards;
      opacity: 0.9;
      z-index: 0;
    }

    @keyframes fall {
      0% {
        transform: translateY(0) rotate(0deg);
        opacity: 1;
      }
      100% {
        transform: translateY(110vh) rotate(360deg);
        opacity: 0;
      }
    }

    /* Popup */
    .popup {
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%) scale(0);
      background: white;
      border-radius: 20px;
      box-shadow: 0 4px 25px rgba(0,0,0,0.2);
      padding: 30px 40px;
      text-align: center;
      transition: transform 0.5s ease;
      z-index: 10;
    }

    .popup.show {
      transform: translate(-50%, -50%) scale(1);
    }

    .popup h2 {
      font-family: 'Dancing Script', cursive;
      color: #d81b60;
      font-size: 2em;
    }

    @keyframes fadeIn {
      from {opacity: 0; transform: translateY(20px);}
      to {opacity: 1; transform: translateY(0);}
    }

    @media (max-width: 600px) {
      h1 { font-size: 2em; }
      button { font-size: 1em; padding: 10px 20px; }
      .popup { width: 80%; }
    }
  </style>
</head>
<body>

  <h1>“Aku mencintaimu selamanya ❤️”</h1>
  <button id="loveBtn">Klik untuk kejutan</button>

  <div class="popup" id="popup">
    <h2>“Kamu adalah alasan aku tersenyum setiap hari 💕”</h2>
  </div>

  <script>
    // Buat hati jatuh terus menerus
    function createHeart() {
      const heart = document.createElement('div');
      heart.classList.add('heart');
      heart.textContent = '❤️';
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.animationDuration = (3 + Math.random() * 2) + 's';
      heart.style.fontSize = (12 + Math.random() * 24) + 'px';
      document.body.appendChild(heart);

      setTimeout(() => {
        heart.remove();
      }, 5000);
    }

    setInterval(createHeart, 300);

    // Popup kejutan
    const btn = document.getElementById('loveBtn');
    const popup = document.getElementById('popup');

    btn.addEventListener('click', () => {
      popup.classList.add('show');
      setTimeout(() => popup.classList.remove('show'), 3000);
    });
  </script>
</body>
</html>

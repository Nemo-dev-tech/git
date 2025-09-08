<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>💌 Happy Birthday คุณแม่ 💌</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Prompt:wght@400;600&display=swap');

    body {
      font-family: 'Prompt', sans-serif;
      background: linear-gradient(135deg, #fff0f6, #ffe6cc);
      margin: 0;
      padding: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }

    .envelope {
      position: relative;
      width: 300px;
      height: 200px;
      background: #ffcc99;
      border-radius: 10px;
      cursor: pointer;
      box-shadow: 0 8px 20px rgba(0,0,0,0.2);
    }

    .flap {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 50%;
      background: #ff9966;
      clip-path: polygon(0 0, 100% 0, 50% 100%);
      transition: transform 0.6s ease;
      transform-origin: top;
    }

    .message {
      display: none;
      background: #fff8f0;
      padding: 20px;
      border-radius: 15px;
      text-align: center;
      box-shadow: 0 8px 20px rgba(255, 153, 102, 0.4);
      max-width: 350px;
      animation: fadeIn 1s ease forwards;
    }

    .message h2 {
      color: #e65c00;
      margin-bottom: 10px;
    }

    .message p {
      color: #333;
      font-size: 16px;
      line-height: 1.6;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }

    .hidden { display: none; }
  </style>
</head>
<body>

  <!-- ซอง -->
  <div class="envelope" id="envelope">
    <div class="flap" id="flap"></div>
  </div>

  <!-- ข้อความอวยพร -->
  <div class="message hidden" id="message">
    <h2>💐 สุขสันต์วันเกิดครับ 💐</h2>
    <p>ขอให้คุณแม่มีความสุขมาก ๆ<br>
    สุขภาพแข็งแรง 💖<br>
    และมีรอยยิ้มทุก ๆ วัน เงินทองไหลมาเทมา 🌸🎂🎁</p>
  </div>

  <!-- เพลง -->
  <audio id="bg-music" loop>
    <source src="happy_birthday.mp3" type="audio/mpeg">
  </audio>

  <script>
    const envelope = document.getElementById("envelope");
    const flap = document.getElementById("flap");
    const message = document.getElementById("message");
    const music = document.getElementById("bg-music");

    envelope.addEventListener("click", () => {
      // เปิดปีกซอง
      flap.style.transform = "rotateX(-180deg)";
      setTimeout(() => {
        envelope.style.display = "none"; // ซ่อนซอง
        message.style.display = "block"; // แสดงข้อความ
        music.play(); // เล่นเพลง
      }, 600);
    });
  </script>

</body>
</html>

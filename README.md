<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Chúc mừng 20/10/2026</title>
  <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Quicksand:wght@500;700&display=swap" rel="stylesheet">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(135deg, #ff9a9e 0%, #fecfef 99%, #fecfef 100%);
      font-family: 'Quicksand', sans-serif;
      overflow: hidden;
    }

    /* Hiệu ứng trái tim bay background */
    .heart-container {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
    }

    .floating-heart {
      position: absolute;
      color: rgba(255, 255, 255, 0.8);
      animation: floatUp 6s linear infinite;
    }

    @keyframes floatUp {
      0% {
        transform: translateY(100vh) scale(0.5);
        opacity: 1;
      }
      100% {
        transform: translateY(-10vh) scale(1.2);
        opacity: 0;
      }
    }

    /* Khung thiệp 3D */
    .card-wrapper {
      perspective: 1000px;
    }

    .card {
      width: 320px;
      height: 440px;
      position: relative;
      transform-style: preserve-3d;
      transition: transform 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275);
      cursor: pointer;
    }

    .card.open {
      transform: rotateY(180deg);
    }

    .card-front, .card-inside {
      position: absolute;
      width: 100%;
      height: 100%;
      backface-visibility: hidden;
      border-radius: 20px;
      box-shadow: 0 15px 35px rgba(0,0,0,0.15);
      padding: 30px;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
    }

    /* Mặt trước */
    .card-front {
      background: #ffffff;
      border: 3px solid #ff758c;
    }

    .card-front .icon {
      font-size: 60px;
      margin-bottom: 15px;
      animation: pulse 1.5s infinite;
    }

    .card-front h2 {
      font-family: 'Dancing Script', cursive;
      font-size: 32px;
      color: #ff4b2b;
    }

    .click-hint {
      margin-top: 15px;
      font-size: 13px;
      color: #888;
    }

    /* Mặt trong */
    .card-inside {
      background: #ffffff;
      border: 3px solid #ff758c;
      transform: rotateY(180deg);
    }

    .date-title {
      color: #ff4b2b;
      font-size: 18px;
      margin-bottom: 15px;
      font-weight: 700;
    }

    .message {
      color: #4a4a4a;
      font-size: 14px;
      line-height: 1.6;
    }

    .signature {
      margin-top: 20px;
      font-family: 'Dancing Script', cursive;
      font-size: 26px;
      color: #ff758c;
    }

    @keyframes pulse {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.1); }
    }
  </style>
</head>
<body>
  <div class="heart-container" id="heartContainer"></div>

  <div class="card-wrapper">
    <div class="card" onclick="toggleCard()">
      <!-- Mặt ngoài của thiệp -->
      <div class="card-front">
        <div class="icon">💌</div>
        <h2>Gửi Một Nửa Thế Giới!</h2>
        <p class="click-hint">(Chạm để mở thiệp ✨)</p>
      </div>

      <!-- Mặt trong của thiệp -->
      <div class="card-inside">
        <h3 class="date-title">Hôm nay là ngày 20/10/2026</h3>
        <p class="message">
          Nhân ngày Phụ nữ Việt Nam 20/10, xin gửi những lời chúc tốt đẹp nhất đến tất cả những người phụ nữ Việt Nam! 🌸<br><br>
          Chúc các chị, các cô và các bạn luôn mạnh khỏe, xinh đẹp, hạnh phúc và thành công rực rỡ trong cuộc sống! ✨
        </p>
        <div class="signature">With love 💕</div>
      </div>
    </div>
  </div>

  <script>
    // Thao tác mở/đóng thiệp
    function toggleCard() {
      const card = document.querySelector('.card');
      card.classList.toggle('open');
    }

    // Tạo hiệu ứng hoa bay ngẫu nhiên
    function createHeart() {
      const heart = document.createElement('div');
      heart.classList.add('floating-heart');
      heart.innerHTML = '🌸';
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.animationDuration = Math.random() * 3 + 3 + 's';
      heart.style.fontSize = Math.random() * 15 + 15 + 'px';

      document.getElementById('heartContainer').appendChild(heart);

      setTimeout(() => {
        heart.remove();
      }, 6000);
    }

    setInterval(createHeart, 300);
  </script>
</body>
</html>

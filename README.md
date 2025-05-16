<!DOCTYPE html>
<html lang="hu">
<head>
  <meta charset="UTF-8" />
  <title>Póló Bolt</title>
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background: #0f0f0f;
      color: #fff;
    }

    header {
      background: #1a1a1a;
      padding: 20px;
      text-align: center;
      font-size: 2rem;
      color: #00ffcc;
    }

    .gallery {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 20px;
      padding: 40px;
    }

    .shirt {
      background: #1e1e1e;
      border-radius: 15px;
      overflow: hidden;
      cursor: pointer;
      transition: transform 0.2s;
    }

    .shirt:hover {
      transform: scale(1.05);
    }

    .shirt img {
      width: 100%;
      height: 250px;
      object-fit: cover;
    }

    .modal {
      display: none;
      position: fixed;
      z-index: 10;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background: rgba(0, 0, 0, 0.9);
      justify-content: center;
      align-items: center;
      flex-direction: column;
      text-align: center;
      padding: 20px;
    }

    .modal img {
      max-width: 90%;
      max-height: 400px;
      border-radius: 10px;
    }

    .modal h2 {
      margin: 20px 0 10px;
      color: #00ffcc;
    }

    .modal p {
      font-size: 1.2rem;
      color: #fff;
    }

    .close {
      position: absolute;
      top: 20px;
      right: 30px;
      font-size: 2rem;
      color: #fff;
      cursor: pointer;
    }
  </style>
</head>
<body>

  <header>👕 Menő Pólóbolt</header>

  <div class="gallery">
    <!-- Póló 1 -->
    <div class="shirt" onclick="showModal('alienhead.jpg', 'AlienHead Póló', '4500 Ft')">
      <img src="alienhead.jpg" alt="AlienHead Póló">
    </div>

    <!-- Üres helyek -->
    <div class="shirt" onclick="showModal('ures.jpg', 'Üres Hely', '4500 Ft')">
      <img src="ures.jpg" alt="Üres Póló">
    </div>

    <div class="shirt" onclick="showModal('ures.jpg', 'Üres Hely', '4500 Ft')">
      <img src="ures.jpg" alt="Üres Póló">
    </div>
  </div>

  <!-- Modal (nagy kép + infó) -->
  <div class="modal" id="modal">
    <span class="close" onclick="closeModal()">&times;</span>
    <img id="modalImg" src="" alt="Póló">
    <h2 id="modalTitle"></h2>
    <p id="modalPrice"></p>
  </div>

  <script>
    function showModal(image, title, price) {
      document.getElementById('modalImg').src = image;
      document.getElementById('modalTitle').textContent = title;
      document.getElementById('modalPrice').textContent = price;
      document.getElementById('modal').style.display = 'flex';
    }

    function closeModal() {
      document.getElementById('modal').style.display = 'none';
    }
  </script>

</body>
</html>

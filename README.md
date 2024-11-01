<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Trang Web Của Bạn</title>
    <link rel="stylesheet" href="style.css" />
    <style>
      body {
        background-color: #000; /* Nền đen */
        color: #fff; /* Màu chữ trắng để dễ đọc trên nền đen */
      }
      .title span {
        font-size: 1.5em; /* Kích thước chữ 1.5em */
      }
      .container {
        text-align: center;
        padding: 20px;
      }
      .cat-img {
        max-width: 100%;
        height: auto;
      }
      .buttons {
        margin-top: 20px;
        position: relative;
      }
      .btn {
        padding: 10px 20px;
        margin: 5px;
        font-size: 1em;
        cursor: pointer;
        position: absolute;
      }
      .btn--yes {
        background-color: #4caf50;
        color: white;
        position: static; /* Giữ nút "Em chấp nhận" ở vị trí cố định */
      }
      .btn--no {
        background-color: #f44336;
        color: white;
      }
      .thank-you-message {
        display: none;
        font-size: 2em;
        text-align: center;
        margin-top: 20px;
      }
    </style>
  </head>
  <body>
    <main class="container">
      <img
        class="cat-img"
        src="https://media.giphy.com/media/SVkhYVCi8fKPKvypi6/giphy.gif"
        alt="Picture of a cat"
      />
      <p class="title">
        Bé iuu ơi choo anhh xinn lỗi nhóooo😭<br /><span class="subtitle"
          >Bé hong chọn hoặc thoát là tha lỗi cho anh đó</span
        >
      </p>
      <div class="buttons">
        <button type="button" class="btn btn--yes">Em chấp nhận</button>
        <button type="button" class="btn btn--no">Không bao giờ</button>
      </div>
      <div class="thank-you-message">
        <img class="new-img" src="https://scontent.xx.fbcdn.net/v/t39.1997-6/45213326_338937646925894_4635366144520224768_n.webp?_nc_cat=1&ccb=1-7&_nc_sid=1176f5&_nc_eui2=AeG6CKoRKSRTxzLJ-skdiaxa-QtBQO6XBGD5C0FA7pcEYI15izAoQnD_emb2B2t4hBcB-tE0hO5qw4Tpi7P9G9oL&_nc_ohc=s2QEwD44kPwQ7kNvgEyrSDd&_nc_ad=z-m&_nc_cid=0&_nc_zt=26&_nc_ht=scontent.xx&_nc_gid=AH4fX0O9vhoIwibeB4Ghs7N&oh=00_AYAYNarQjeR7gHPWh12PNfcNHiqHren68s3SD0oUo5ksEw&oe=672AFB6D" alt="New Image" />
        <p>Cảm ơn em đã tha lỗi cho anh, anh yêu em nhiều lắm ❤️❤️❤️</p>
        <p>Xin lỗi vì làm em buồn nha bé, anh tự phạt bằng cách mua cho bé ly trà sữa nha ❤️❤️❤️</p>

      </div>
    </main>

    <script>
      let noClickCount = 0;

      document.querySelector('.btn--yes').addEventListener('click', function() {
        document.querySelector('.title').style.display = 'none';
        document.querySelector('.buttons').style.display = 'none';
        document.querySelector('.cat-img').style.display = 'none';
        document.querySelector('.thank-you-message').style.display = 'block';
      });

      document.querySelector('.btn--no').addEventListener('click', function() {
        const button = document.querySelector('.btn--no');
        const container = document.querySelector('.container');
        const containerRect = container.getBoundingClientRect();
        const buttonRect = button.getBoundingClientRect();

        // Tạo vị trí ngẫu nhiên trong phạm vi của container
        const randomX = Math.random() * (containerRect.width - buttonRect.width);
        const randomY = Math.random() * (containerRect.height - buttonRect.height);

        // Đặt vị trí mới cho nút
        button.style.left = `${randomX}px`;
        button.style.top = `${randomY}px`;

        // Tăng số lần nhấn nút "Không bao giờ"
        noClickCount++;

        // Thay đổi dòng chữ sau khi nhấn quá 5 lần
        if (noClickCount > 5) {
          document.querySelector('.subtitle').textContent = 'Tha lỗi cho anh nha, đừng nhấn không chấp nhận nữa🥹🥹';
        }
      });
    </script>
  </body>
</html>

<!DOCTYPE html>
<html>
<head>
  <title>Agen 2captcha</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
    }
    
    .container {
      max-width: 960px;
      margin: 0 auto;
      padding: 20px;
    }
    
    .form-container {
      margin-top: 20px;
    }
    
    .form-container h3 {
      margin-bottom: 10px;
    }
    
    .form-container input[type="email"] {
      width: 100%;
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    
    .logo-container {
      text-align: center;
      margin-top: 20px;
    }
    
    .logo-container img {
      width: 250px;
      height: 250px;
      cursor: pointer;
    }
    
    .amount-container {
      display: flex;
      justify-content: space-between;
      margin-top: 20px;
    }
    
    .amount-container input[type="number"] {
      width: calc(60% - 10px);
      padding: 14px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    
    .amount-container .result-box {
      width: calc(50% - 10px);
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 5px;
      text-align: center;
    }
    
    .payment-container {
      display: flex;
      justify-content: space-between;
      margin-top: 20px;
    }
    
    .payment-container .payment-option {
      display: flex;
      flex-direction: column;
      align-items: center;
      text-align: center;
    }
    
    .payment-container .payment-option .payment-logo {
      width: 85px;
      height: 85px;
      margin-bottom: 10px;
      cursor: pointer;
      background-repeat: no-repeat;
      background-size: contain;
      background-position: center;
    }

    .payment-container .payment-option .payment-logo.bri {
      background-image: url("https://i.ibb.co/XL7jwVL/logo-bri.png");
    }
    .payment-container .payment-option .payment-logo.mandiri {
      background-image: url("https://i.ibb.co/tZ4sLNN/logo-mandiri.png");
    }
    .payment-container .payment-option .payment-logo.bca {
      background-image: url("https://i.ibb.co/7CHzvcP/logo-bca.png");
    }
    .payment-container .payment-option .payment-logo.dana {
      background-image: url("https://i.ibb.co/yShHhQ5/logo-dana.png");
    }
    .payment-container .payment-option .payment-logo.ovo {
      background-image: url("https://i.ibb.co/99XY0Wz/logo-ovo.png");
    }
    .payment-container .payment-option .payment-logo.gopay {
      background-image: url("https://i.ibb.co/YQHLShw/logo-gopay.png");
    }

    .request-box {
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      text-align: center;
      margin-top: 20px;
    }

    .request-box button {
      padding: 22px 32px;
      border: none;
      background-color: #333;
      color: #fff;
      border-radius: 5px;
      cursor: pointer;
    }
  </style>

</head>
<body>

  <div class="logo-container">
    <a href="#"><img src="https://i.ibb.co/CVJrfyH/logo-convert.png" alt="Logo Convert"></a>
  </div>
  
  <div class="container">
    <div class="form-container">
      <h3>Gmail 2captcha Anda</h3>
      <input type="email" placeholder="Masukkan alamat Gmail">
    </div>
    
    <div class="amount-container">
      <div>
        <h3>Jumlah 1 = 1$ Dollar</h3>
        <input type="number" id="jumlah-input" placeholder="Masukkan jumlah" min="1" value="0" required>
      </div>
    <div class="result-box">
    <h3>Jumlah yang Diperoleh</h3>
    <p id="result"></p>
    <div id="currency-widget"></div>
    </div>
    </div>

<div class="payment-container">
  <div class="payment-option">
    <input type="radio" name="payment" id="bri" value="bri" onclick="selectPayment('bri')">
    <label for="bri" class="payment-logo bri"></label>
  </div>
  <div class="payment-option">
    <input type="radio" name="payment" id="mandiri" value="mandiri" onclick="selectPayment('mandiri')">
    <label for="mandiri" class="payment-logo mandiri"></label>
  </div>
  <div class="payment-option">
    <input type="radio" name="payment" id="bca" value="bca" onclick="selectPayment('bca')">
    <label for="bca" class="payment-logo bca"></label>
  </div>
  <div class="payment-option">
    <input type="radio" name="payment" id="dana" value="dana" onclick="selectPayment('dana')">
    <label for="dana" class="payment-logo dana"></label>
  </div>
  <div class="payment-option">
    <input type="radio" name="payment" id="ovo" value="ovo" onclick="selectPayment('ovo')">
    <label for="ovo" class="payment-logo ovo"></label>
  </div>
  <div class="payment-option">
    <input type="radio" name="payment" id="gopay" value="gopay" onclick="selectPayment('gopay')">
    <label for="gopay" class="payment-logo gopay"></label>
  </div>
</div>


    <div class="request-box">
    <button onclick="kirimPermintaan()">Kirim Permintaan</button>
  </div>
</div>


  <script>
    function kirimPermintaan() {
      const gmailInput = document.getElementById('gmail-input');
      const jumlahInput = document.getElementById('jumlah-input');
      const selectedPayment = document.querySelector('input[name="payment"]:checked');

      if (gmailInput.value && jumlahInput.value && selectedPayment) {
        const gmail = encodeURIComponent(gmailInput.value);
        const jumlah = encodeURIComponent(jumlahInput.value);
        const metode = encodeURIComponent(selectedPayment.value);

        // Redirect ke halaman admin dengan parameter yang sesuai
        window.location.href = `https://chatcaptchakings.blogspot.com/p/admin.html?gmail=${gmail}&jumlah=${jumlah}&metode=${metode}`;
      } else {
        alert('Lengkapi semua field terlebih dahulu');
      }
    }

    const jumlahInput = document.getElementById('jumlah-input');
    const resultBox = document.getElementById('result');
    let selectedPayment = '';

    jumlahInput.addEventListener('input', function() {
      const jumlah = parseInt(jumlahInput.value);
      if (!isNaN(jumlah)) {
        const jumlahDiperoleh = jumlah * 13000;
        resultBox.textContent = "Rp " + jumlahDiperoleh.toLocaleString();
      } else {
        resultBox.textContent = '';
      }
    });

    function selectPayment(payment) {
      selectedPayment = payment;
      resetPaymentOptions();
      const paymentOption = document.getElementById(payment);
      paymentOption.classList.add('selected');
    }

    function resetPaymentOptions() {
      const paymentOptions = document.getElementsByClassName('payment-option');
      for (let i = 0; i < paymentOptions.length; i++) {
        paymentOptions[i].classList.remove('selected');
      }
    }

    function kirimPermintaan() {
      if (selectedPayment !== '') {
        // Lakukan logika pengiriman permintaan ke server dengan metode pembayaran yang dipilih
        console.log('Permintaan dikirim dengan metode pembayaran ' + selectedPayment);
      } else {
        alert('Pilih metode pembayaran terlebih dahulu');
      }
    }
    
  </script>

</body>
</html>

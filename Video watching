<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Video Watching Bot</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background-color: #121212;
      color: #fff;
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }
    .container {
      text-align: center;
      background: #1f1f1f;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.5);
      width: 300px;
    }
    .container h1 {
      font-size: 20px;
      color: green;
      margin-bottom: 10px;
    }
    .developer {
      font-size: 12px;
      background-color: green;
      padding: 5px 10px;
      border-radius: 5px;
      margin-bottom: 15px;
      display: inline-block;
      cursor: pointer;
    }
    .stats, .user-info {
      margin: 10px 0;
    }
    .stats p, .user-info p {
      margin: 5px 0;
      font-size: 14px;
    }
    .progress-circle {
      width: 80px;
      height: 80px;
      border: 4px solid green;
      border-radius: 50%;
      display: flex;
      justify-content: center;
      align-items: center;
      margin: 10px auto;
    }
    .progress-circle span {
      font-size: 18px;
      font-weight: bold;
    }
    .buttons button {
      width: 90%;
      margin: 5px 0;
      padding: 10px;
      font-size: 14px;
      border: none;
      border-radius: 5px;
      color: white;
      background: green;
      cursor: pointer;
    }
    .buttons button:hover {
      background: darkorange;
    }
    .withdraw-section {
      margin-top: 20px;
      display: none;
      padding: 20px;
      background-color: #2a2a2a;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.5);
    }
    .withdraw-section input,
    .withdraw-section select {
      width: 100%;
      padding: 12px;
      margin: 8px 0;
      border-radius: 5px;
      border: 2px solid #555;
      background-color: #333;
      color: #fff;
    }
    .withdraw-section input:focus,
    .withdraw-section select:focus {
      border-color: green;
      outline: none;
    }
    .withdraw-section button {
      background-color: green;
      width: 100%;
      padding: 12px;
      font-size: 16px;
      margin-top: 15px;
      border-radius: 5px;
      cursor: pointer;
    }
    .withdraw-section button:hover {
      background-color: #006400;
    }
    #withdraw-status {
      color: red;
      font-size: 14px;
      margin-top: 10px;
    }
  </style>
  <script src='//libtl.com/sdk.js' data-zone='9467350' data-sdk='show_9467350'></script>
</head>
<body>
  <div class="container">
    <h1>Video Watching Bot</h1>
    <div class="developer" onclick="window.location.href='https://t.me/Bossmaster100'">Developer by Crush king</div>
    <div class="user-info">
      <p>Welcome, <span id="user-name"></span></p>
    </div>
    <div class="stats">
      <p>Video Watching: <span id="watched-ads">0</span></p>
      <p>Earned Points: <span id="earned-points">0</span></p>
    </div>
    <div class="progress-circle">
      <span id="ads-progress">0%</span>
    </div>
    <div class="buttons">
      <button onclick="watchAd()">🎥 Watch Video</button>
      <button onclick="startAutoAds()">🎬 Watch Video (Auto)</button>
      <button onclick="stopAutoAds()">⏹️ Stop Video</button>
      <button onclick="showWithdrawForm()">Withdraw</button>
    </div>
    <div class="withdraw-section" id="withdraw-section">
      <h3 style="color: orange; margin-bottom: 15px;">Withdrawal Request</h3>
      <input type="number" id="withdraw-amount" placeholder="Enter Points to Withdraw" />
      <select id="payment-method">
        <option value="bkash">Bkash</option>
        <option value="nagad">Nagad</option>
        <option value="manual">Manual</option>
      </select>
      <input type="text" id="withdraw-phone" placeholder="Enter Phone Number" />
      <button onclick="withdrawPoints()">Withdraw</button>
      <p id="withdraw-status"></p>
    </div>
  </div>
  <script>
    const MIN_WITHDRAW_POINTS = 5;
    const ADMIN_USER_ID = 6665642603;
    const BOT_TOKEN = "7979248852:AAF7Gee5sWLe41_jK4G_jJHRoXGlo39gZ5k";
    let watchedAdsCount = 0;
    let earnedPoints = 0.00;
    let autoAdInterval;const telegramUserName = "@exampleUser";
document.getElementById("user-name").textContent = telegramUserName;

if (localStorage.getItem('watchedAdsCount')) {
  watchedAdsCount = parseInt(localStorage.getItem('watchedAdsCount'));
  earnedPoints = parseFloat(localStorage.getItem('earnedPoints'));
  document.getElementById('watched-ads').textContent = watchedAdsCount;
  document.getElementById('earned-points').textContent = earnedPoints.toFixed(2);
}

function watchAd() {
  if (typeof show_9467350 === 'function') {
    show_9467350().then(() => {
      watchedAdsCount++;
      earnedPoints += 0.50;
      document.getElementById('watched-ads').textContent = watchedAdsCount;
      document.getElementById('earned-points').textContent = earnedPoints.toFixed(2);
      localStorage.setItem('watchedAdsCount', watchedAdsCount);
      localStorage.setItem('earnedPoints', earnedPoints.toFixed(2));
      updateProgressCircle();
    });
  }
}

function updateProgressCircle() {
  const percentage = (watchedAdsCount / 10) * 100;
  document.getElementById('ads-progress').textContent = `${percentage}%`;
}

function startAutoAds() {
  autoAdInterval = setInterval(watchAd, 5000);
}

function stopAutoAds() {
  clearInterval(autoAdInterval);
}

function showWithdrawForm() {
  document.getElementById('withdraw-section').style.display = 'block';
}

function withdrawPoints() {
  const amount = document.getElementById('withdraw-amount').value;
  const paymentMethod = document.getElementById('payment-method').value;
  const phoneNumber = document.getElementById('withdraw-phone').value;

  if (amount < MIN_WITHDRAW_POINTS) {
    document.getElementById('withdraw-status').textContent = `Minimum withdrawal amount is ${MIN_WITHDRAW_POINTS} points.`;
    return;
  }

  if (amount > earnedPoints) {
    document.getElementById('withdraw-status').textContent = `Insufficient balance. You have ${earnedPoints.toFixed(2)} points.`;
    return;
  }

  earnedPoints -= parseFloat(amount);
  document.getElementById('earned-points').textContent = earnedPoints.toFixed(2);
  localStorage.setItem('earnedPoints', earnedPoints.toFixed(2));

  const message = `Withdrawal Request from ${telegramUserName}:%0AAmount: ${amount} points%0APayment Method: ${paymentMethod}%0APhone Number: ${phoneNumber}`;

  fetch(`https://api.telegram.org/bot${BOT_TOKEN}/sendMessage?chat_id=${ADMIN_USER_ID}&text=${message}`)
    .then(response => response.json())
    .then(data => {
      if (data.ok) {
        document.getElementById('withdraw-status').textContent = 'Withdrawal request sent successfully!';
      } else {
        document.getElementById('withdraw-status').textContent = 'Failed to send request.';
      }
    })
    .catch(error => {
      console.error('Error:', error);
      document.getElementById('withdraw-status').textContent = 'An error occurred.';
    });
}

  </script>
</body>
</html>

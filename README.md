<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Countdown to 9/17/2025</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      padding-top: 50px;
      background: #f0f0f0;
    }
    #countdown {
      font-size: 2em;
      background: white;
      padding: 20px;
      border-radius: 10px;
      display: inline-block;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }
  </style>
</head>
<body>

<h1>Countdown to Trip! ✈️</h1>
<div id="countdown"></div>

<script>
  const countdownElement = document.getElementById('countdown');
  const targetDate = new Date('September 17, 2025 10:00:00').getTime();

  function updateCountdown() {
    const now = new Date().getTime();
    const distance = targetDate - now;

    if (distance < 0) {
      countdownElement.innerHTML = "🎉 It's time!";
      clearInterval(interval);
      return;
    }

    const days = Math.floor(distance / (1000 * 60 * 60 * 24));
    const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
    const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
    const seconds = Math.floor((distance % (1000 * 60)) / 1000);

    countdownElement.innerHTML = `
      ${days}d ${hours}h ${minutes}m ${seconds}s
    `;
  }

  updateCountdown(); // run once immediately
  const interval = setInterval(updateCountdown, 1000); // then every second
</script>

</body>
</html>

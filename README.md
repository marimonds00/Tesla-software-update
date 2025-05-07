<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Software Update</title>
  <style>
    body {
      background-color: #000;
      color: #fff;
      font-family: "Helvetica Neue", sans-serif;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      text-align: center;
      padding: 20px;
    }
    #logo {
      width: 100px;
      margin-bottom: 20px;
    }
    #status {
      font-size: 28px;
      margin-bottom: 10px;
    }
    #timer {
      font-size: 36px;
      letter-spacing: 2px;
    }
    #result {
      display: none;
      flex-direction: column;
      align-items: center;
      margin-top: 30px;
    }
    #custom-car {
      margin-top: 20px;
      max-width: 90%;
      border-radius: 12px;
      box-shadow: 0 0 20px rgba(255, 255, 255, 0.2);
    }
    a {
      color: #00c8ff;
      text-decoration: none;
      font-size: 24px;
      margin-top: 20px;
    }
    a:hover {
      text-decoration: underline;
    }
  </style>
</head>
<body>

  <img id="logo" src="https://upload.wikimedia.org/wikipedia/commons/b/bd/Tesla_Motors.svg" alt="Tesla Logo" />
  <div id="status">Software update in process</div>
  <div id="timer">10:00</div>

  <div id="result">
    <h2>Your Tesla is ready!</h2>
    <img id="custom-car" src="https://via.placeholder.com/600x300?text=Your+Tesla" alt="Custom Tesla"/>
    <a href="https://example.com/car-images" target="_blank">Click here to view your custom Tesla</a>
  </div>

  <script>
    let totalSeconds = 600;
    const timerDisplay = document.getElementById("timer");
    const resultDisplay = document.getElementById("result");
    const statusDisplay = document.getElementById("status");

    const countdown = setInterval(() => {
      totalSeconds--;
      const minutes = Math.floor(totalSeconds / 60);
      const seconds = totalSeconds % 60;
      timerDisplay.textContent = `${minutes.toString().padStart(2, '0')}:${seconds.toString().padStart(2, '0')}`;
      
      if (totalSeconds <= 0) {
        clearInterval(countdown);
        timerDisplay.style.display = "none";
        statusDisplay.style.display = "none";
        resultDisplay.style.display = "flex";
      }
    }, 1000);
  </script>

</body>
</html>

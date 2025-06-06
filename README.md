<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Forgive or Not?</title>
  <style>
    body {
      background: #fff0f6;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      font-family: Arial, sans-serif;
    }
    .envelope-container {
      position: relative;
      width: 200px;
      height: 120px;
      cursor: pointer;
    }
    .envelope {
      width: 100%;
      height: 100%;
      background: #ff9ecf;
      position: relative;
      overflow: hidden;
      border-radius: 5px;
      transition: transform 0.5s;
    }
    .envelope:before {
      content: "";
      position: absolute;
      top: -60px;
      left: 0;
      width: 100%;
      height: 120px;
      background: #ffb3da;
      transform-origin: bottom;
      transition: transform 0.5s;
    }
    .envelope.open:before {
      transform: rotateX(180deg);
    }
    .message-box {
      position: absolute;
      top: 10px;
      left: 10px;
      right: 10px;
      bottom: 10px;
      background: #fff;
      display: none;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      border-radius: 3px;
      text-align: center;
      padding: 10px;
      box-shadow: 0 0 5px rgba(0,0,0,0.2);
    }
    .message-box.active {
      display: flex;
    }
    .message-box button {
      margin: 5px;
      padding: 8px 12px;
      border: none;
      background: #ff9ecf;
      color: #fff;
      border-radius: 3px;
      cursor: pointer;
    }
    .message {
      margin-top: 10px;
      font-weight: bold;
      color: #333;
    }
  </style>
</head>
<body>

<div class="envelope-container">
  <div class="envelope" id="envelope"></div>
  <div class="message-box" id="options">
    <div>🥀 What will you choose?</div>
    <button id="forgiveBtn">Forgive him</button>
    <button id="notForgiveBtn">Do not forgive him</button>
  </div>
  <div class="message-box" id="forgiveMsg">
    <div class="message">Thank you Zamy, I really love you—please come back 💖</div>
  </div>
  <div class="message-box" id="dontForgiveMsg">
    <div class="message">You have to forgive him</div>
    <button id="okBtn">Okay</button>
  </div>
</div>

<script>
  const envelope = document.getElementById("envelope");
  const options = document.getElementById("options");
  const forgiveBtn = document.getElementById("forgiveBtn");
  const notForgiveBtn = document.getElementById("notForgiveBtn");
  const forgiveMsg = document.getElementById("forgiveMsg");
  const dontForgiveMsg = document.getElementById("dontForgiveMsg");
  const okBtn = document.getElementById("okBtn");

  envelope.addEventListener("click", () => {
    envelope.classList.add("open");
    options.classList.add("active");
  });

  forgiveBtn.addEventListener("click", () => {
    options.classList.remove("active");
    forgiveMsg.classList.add("active");
  });

  notForgiveBtn.addEventListener("click", () => {
    options.classList.remove("active");
    dontForgiveMsg.classList.add("active");
  });

  okBtn.addEventListener("click", () => {
    dontForgiveMsg.classList.remove("active");
    forgiveMsg.classList.add("active");
  });
</script>

</body>
</html>


<!---
vmfmd/vmfmd is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->

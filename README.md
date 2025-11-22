 <!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Important System Alert</title>
  <style>
    body {
      background-color: black;
      color: limegreen;
      font-family: monospace;
      text-align: center;
      padding-top: 100px;
      overflow: hidden;
    }
    #message {
      font-size: 40px; /* Larger text */
      font-weight: bold; /* Bold text */
      margin-bottom: 20px;
      position: relative;
      z-index: 2;
    }
    #surprise {
      display: none;
      font-size: 48px; /* Larger text */
      font-weight: bold;
      color: yellow;
      position: relative;
      z-index: 2;
    }
    .animal {
      position: absolute;
      top: 0;
      font-size: 30px;
      animation: fly 12s linear infinite;
      z-index: 1;
    }
    @keyframes fly {
      from { transform: translateX(-100vw); }
      to { transform: translateX(100vw); }
    }
    #prankButton {
      position: fixed;
      top: 10px;
      left: 50%;
      transform: translateX(-50%);
      background-color: red;
      color: white;
      font-size: 20px;
      font-weight: bold;
      padding: 10px 20px;
      border: none;
      cursor: pointer;
      z-index: 3;
    }
  </style>
  <script>
    function prank() {
      let msg = document.getElementById("message");
      let surprise = document.getElementById("surprise");

      msg.innerText = "⚠️ parh le behen chod! mader chod parh le baad me dekhin tiktok penlun ⚠️";

      // After 6 seconds, change the message
      setTimeout(() => {
        msg.innerText = "tere saath koi ni set hone waali parh le!!!!!!!";
      }, 6000);

      // After another 6 seconds (total 12), show the surprise
      setTimeout(() => {
        msg.style.display = "none";
        surprise.style.display = "block";
      }, 12000);

      // Generate birds, dogs, and cats
      let animals = ["🐦", "🐕", "🐈"];
      for (let i = 0; i < 150; i++) {
        let animal = document.createElement("div");
        animal.className = "animal";
        animal.innerText = animals[Math.floor(Math.random() * animals.length)];
        animal.style.top = Math.random() * window.innerHeight + "px";
        animal.style.animationDuration = (5 + Math.random() * 10) + "s";
        animal.style.fontSize = (20 + Math.random() * 25) + "px";
        document.body.appendChild(animal);
      }
    }
    window.onload = prank;
  </script>
</head>
<body>
  <button id="prankButton">mids a gaye gairet ni ayi tujhe</button>
  <div id="message">Loading...</div>
  <div id="surprise">kiun time zaya ker raha parh le khusre!!!!</div>
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Important Question 😏</title>
  <style>
    body {
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: #111;
      color: white;
      font-family: Arial, sans-serif;
    }

    .box {
      text-align: center;
    }

    button {
      padding: 12px 25px;
      font-size: 18px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      margin: 10px;
      transition: all 0.2s ease;
    }

    #yes {
      background: #00ff88;
    }

    #no {
      background: #ff4444;
      position: absolute;
    }
  </style>
</head>
<body>

  <div class="box">
    <h1>Wanna play Roblox with me? 🎮</h1>
    <button id="yes" onclick="yesClick()">YES</button>
    <button id="no" onmouseover="runAway()">NO</button>
  </div>

  <script>

  const noBtn = document.getElementById("no");
  const yesBtn = document.getElementById("yes");
  let yesSize = 18;

  function moveNo(x, y) {
    const rect = noBtn.getBoundingClientRect();
    const noX = rect.left + rect.width / 2;
    const noY = rect.top + rect.height / 2;

    const distance = Math.hypot(x - noX, y - noY);

    if (distance < 120) {
      let moveX = noX - x;
      let moveY = noY - y;

      const length = Math.hypot(moveX, moveY);
      moveX = (moveX / length) * 150;
      moveY = (moveY / length) * 150;

      let newX = rect.left + moveX;
      let newY = rect.top + moveY;

      newX = Math.max(0, Math.min(window.innerWidth - rect.width, newX));
      newY = Math.max(0, Math.min(window.innerHeight - rect.height, newY));

      noBtn.style.left = newX + "px";
      noBtn.style.top = newY + "px";

      yesSize += 1.2;
      yesBtn.style.fontSize = yesSize + "px";
    }
  }

  // PC (mouse)
  document.addEventListener("mousemove", (e) => {
    moveNo(e.clientX, e.clientY);
  });

  // Mobile (touch)
  document.addEventListener("touchmove", (e) => {
    const touch = e.touches[0];
    moveNo(touch.clientX, touch.clientY);
  });

  function yesClick() {
    alert("Roblox time 😎🔥");
  }
</script>

  </script>

</body>
</html>


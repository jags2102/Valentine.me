<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>For Sree 💖</title>

<style>
body {
  margin: 0;
  height: 100vh;
  font-family: 'Comic Sans MS', cursive;
  background: linear-gradient(135deg, #ffdde1, #ee9ca7);
  overflow: hidden;
  text-align: center;
}

h1 {
  color: #ff2f6e;
  text-shadow: 2px 2px white;
}

.big-love {
  font-size: 140px;
  animation: pulse 1.5s infinite;
}

@keyframes pulse {
  0% { transform: scale(1); }
  50% { transform: scale(1.15); }
  100% { transform: scale(1); }
}

.van {
  position: absolute;
  left: -320px;
  bottom: 120px;
  font-size: 110px;
  animation: drive 4s forwards;
}

@keyframes drive {
  to { left: 50%; transform: translateX(-50%); }
}

.door {
  display: none;
  font-size: 40px;
}

.gift {
  position: absolute;
  font-size: 35px;
  animation: drop 3s forwards;
}

@keyframes drop {
  0% { top: 200px; opacity: 0; }
  100% { top: 520px; opacity: 1; }
}

.question {
  display: none;
  position: absolute;
  bottom: 40px;
  width: 100%;
}

button {
  padding: 14px 32px;
  font-size: 18px;
  border-radius: 30px;
  border: none;
  cursor: pointer;
}

.yes {
  background: #ff2f6e;
  color: white;
  box-shadow: 0 0 14px #ff2f6e;
}

.no {
  background: #fff;
  position: absolute;
}

.heart {
  position: absolute;
  font-size: 20px;
  animation: float 5s infinite;
}

@keyframes float {
  0% { transform: translateY(0); opacity: 1; }
  100% { transform: translateY(-600px); opacity: 0; }
}

.confetti {
  position: absolute;
  width: 10px;
  height: 10px;
  animation: confettiFall 3s linear forwards;
}

@keyframes confettiFall {
  to { transform: translateY(800px) rotate(360deg); opacity: 0; }
}

.firework {
  position: absolute;
  font-size: 30px;
  animation: explode 1.5s ease-out forwards;
}

@keyframes explode {
  0% { transform: scale(0); opacity: 1; }
  100% { transform: scale(3); opacity: 0; }
}
</style>
</head>

<body>

<div class="van">
  🚐
  <div class="door" id="door">🚪</div>
</div>

<div class="question" id="question">
  <h1>Will you be my Valentine, Sree? 💕</h1>
  <button class="yes" onclick="yesClick()">YES 💖</button>
  <button class="no" id="noBtn">NO 😜</button>
</div>

<script>
// Floating hearts
setInterval(() => {
  let heart = document.createElement("div");
  heart.className = "heart";
  heart.innerHTML = "💗";
  heart.style.left = Math.random() * window.innerWidth + "px";
  heart.style.bottom = "0px";
  document.body.appendChild(heart);
  setTimeout(() => heart.remove(), 5000);
}, 500);

// Open van door
setTimeout(() => {
  document.getElementById("door").style.display = "inline";
}, 4200);

// Drop gifts
setTimeout(() => {
  for (let i = 0; i < 18; i++) {
    let gift = document.createElement("div");
    gift.className = "gift";
    gift.innerHTML = "🎁💝";
    gift.style.left = Math.random() * window.innerWidth + "px";
    document.body.appendChild(gift);
  }
}, 4600);

// Show question
setTimeout(() => {
  document.getElementById("question").style.display = "block";
}, 6200);

// NO button runs away 😈
const noBtn = document.getElementById("noBtn");
noBtn.addEventListener("mouseover", () => {
  noBtn.style.left = Math.random() * (window.innerWidth - 100) + "px";
  noBtn.style.top = Math.random() * (window.innerHeight - 100) + "px";
});

// YES celebration 💖🎆🎊
function yesClick() {
  document.body.innerHTML = `
    <div style="margin-top:60px">
      <div class="big-love">❤️</div>
      <h1>I LOVE YOU SREE 💖</h1>
      <h1>Happy Valentine’s Day 💐</h1>
    </div>
  `;

  // Confetti
  for (let i = 0; i < 160; i++) {
    let c = document.createElement("div");
    c.className = "confetti";
    c.style.left = Math.random() * window.innerWidth + "px";
    c.style.top = "-10px";
    c.style.background = `hsl(${Math.random() * 360},100%,50%)`;
    document.body.appendChild(c);
    setTimeout(() => c.remove(), 3000);
  }

  // Fireworks
  for (let i = 0; i < 25; i++) {
    let f = document.createElement("div");
    f.className = "firework";
    f.innerHTML = "🎆";
    f.style.left = Math.random() * window.innerWidth + "px";
    f.style.top = Math.random() * window.innerHeight + "px";
    document.body.appendChild(f);
    setTimeout(() => f.remove(), 1500);
  }
}
</script>

</body>
</html>

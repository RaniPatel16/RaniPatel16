<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Rani Patel - Portfolio</title>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background: #020b12;
  font-family: 'Segoe UI', sans-serif;
  color: white;
  text-align: center;
  overflow-x: hidden;
}

/* HEADER FIX */
.header {
  height: 220px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 42px;
  font-weight: bold;
  background: linear-gradient(135deg, #0f2027, #203a43, #2c5364);
  transform: perspective(900px) rotateX(8deg);
  animation: floatHeader 6s ease-in-out infinite;
}

@keyframes floatHeader {
  0%,100% { transform: perspective(900px) rotateX(8deg) translateY(0); }
  50% { transform: perspective(900px) rotateX(8deg) translateY(-10px); }
}

/* NAME */
.name {
  margin-top: 40px;
  font-size: 32px;
  color: #ccc;
}

/* FIXED TYPING */
.typing {
  font-size: 22px;
  color: #00c9ff;
  font-family: monospace;
  margin-top: 10px;
}

/* TERMINAL */
.terminal {
  margin: 40px auto;
  padding: 15px;
  background: #111;
  border-radius: 8px;
  width: fit-content;
  box-shadow: 0 0 10px #00c9ff;
  font-family: monospace;
}

/* SECTION */
.section {
  margin: 60px 20px;
}

/* BUTTON FIX (3D clean) */
.btn {
  display: inline-block;
  padding: 12px 25px;
  margin: 10px;
  border: 2px solid #00c9ff;
  color: #00c9ff;
  text-decoration: none;
  border-radius: 8px;
  transition: 0.3s;
}

.btn:hover {
  background: #00c9ff;
  color: black;
  transform: translateY(-6px);
  box-shadow: 0 10px 25px rgba(0,201,255,0.5);
}

/* TECH FIX */
.tech img {
  width: 60px;
  margin: 10px;
  transition: 0.3s;
}

.tech img:hover {
  transform: scale(1.2) translateY(-8px);
  filter: drop-shadow(0 8px 10px #00c9ff);
}

/* CARDS FIX */
.card {
  display: inline-block;
  padding: 15px;
  margin: 10px;
  border: 1px solid #00c9ff;
  background: #0f2027;
  border-radius: 10px;
  transition: 0.3s;
}

.card:hover {
  transform: translateY(-10px);
  box-shadow: 0 10px 20px rgba(0,201,255,0.4);
}
</style>

</head>

<body>

<!-- HEADER -->
<div class="header">Rani Patel</div>

<div class="name">Rani Patel</div>
<div class="typing" id="typing"></div>

<!-- TERMINAL -->
<div class="terminal">
> Initializing Profile... <br>
> Loading Skills... <br>
> Access Granted ✅
</div>

<!-- ABOUT -->
<div class="section">
<h2>About</h2>
<p>
Frontend developer focused on building modern web interfaces and exploring AI-driven solutions.<br>
Currently learning the MERN stack.
</p>
</div>

<!-- PORTFOLIO -->
<div class="section">
<h2>Portfolio</h2>
<a href="#" class="btn">Open Portfolio</a>
</div>

<!-- PROJECTS -->
<div class="section">
<h2>Projects</h2>

<div class="card">BigBasket Clone</div>
<div class="card">Porter Clone</div>
<div class="card">BBC News Clone</div>
<div class="card">AI Chatbot</div>

</div>

<!-- TECH STACK -->
<div class="section">
<h2>Technology Stack</h2>

<div class="tech">
<img src="https://skillicons.dev/icons?i=html">
<img src="https://skillicons.dev/icons?i=css">
<img src="https://skillicons.dev/icons?i=js">
<img src="https://skillicons.dev/icons?i=react">
<img src="https://skillicons.dev/icons?i=nodejs">
<img src="https://skillicons.dev/icons?i=mongodb">
</div>

</div>

<!-- CONTACT -->
<div class="section">
<h2>Contact</h2>

<a href="https://github.com/RaniPatel16" class="btn">GitHub</a>
<a href="#" class="btn">LinkedIn</a>
<a href="#" class="btn">LeetCode</a>

</div>

<!-- FIXED TYPING SCRIPT -->
<script>
const words = ["MERN Stack Developer", "Frontend Developer", "AI Enthusiast"];
let i = 0, j = 0, current = "", isDeleting = false;

function type() {
  current = words[i];

  if (!isDeleting) {
    document.getElementById("typing").innerHTML = current.substring(0, j++);
    if (j > current.length) {
      isDeleting = true;
      setTimeout(type, 1000);
      return;
    }
  } else {
    document.getElementById("typing").innerHTML = current.substring(0, j--);
    if (j === 0) {
      isDeleting = false;
      i = (i + 1) % words.length;
    }
  }

  setTimeout(type, isDeleting ? 50 : 100);
}

type();
</script>

</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Rani Patel Portfolio</title>

<style>
body {
  margin: 0;
  background: #020b12;
  font-family: Arial, sans-serif;
  color: white;
  text-align: center;
}

/* ================= HEADER ================= */
.header {
  height: 200px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 42px;
  font-weight: bold;
  background: linear-gradient(90deg, #0f2027, #203a43, #2c5364);
  transform: perspective(900px) rotateX(12deg);
  animation: float 5s ease-in-out infinite;
}

@keyframes float {
  0%,100% { transform: perspective(900px) rotateX(12deg) translateY(0); }
  50% { transform: perspective(900px) rotateX(12deg) translateY(-10px); }
}

/* ================= NAME ================= */
.name {
  margin-top: 30px;
  font-size: 32px;
  color: #ccc;
}

/* ================= TYPING EFFECT ================= */
.typing {
  font-size: 22px;
  color: #00c9ff;
  font-family: monospace;
  border-right: 3px solid #00c9ff;
  width: fit-content;
  margin: auto;
  white-space: nowrap;
  overflow: hidden;
  animation: typing 4s steps(20), blink 0.5s infinite alternate;
}

@keyframes typing {
  from { width: 0 }
  to { width: 260px }
}

@keyframes blink {
  from { border-color: transparent }
  to { border-color: #00c9ff }
}

/* ================= TERMINAL ================= */
.terminal {
  margin: 40px auto;
  width: fit-content;
  padding: 15px;
  background: #111;
  border-radius: 8px;
  box-shadow: 0 0 10px #00c9ff;
}

/* ================= SECTIONS ================= */
.section {
  margin: 40px 20px;
}

/* ================= 3D BUTTON ================= */
.btn {
  display: inline-block;
  padding: 12px 25px;
  margin: 10px;
  color: #00c9ff;
  text-decoration: none;
  border: 2px solid #00c9ff;
  border-radius: 10px;
  transition: 0.3s;
  transform: perspective(500px) rotateX(0deg);
}

.btn:hover {
  background: #00c9ff;
  color: black;
  transform: perspective(500px) rotateX(15deg) scale(1.1);
  box-shadow: 0 10px 20px rgba(0,201,255,0.5);
}

/* ================= TECH STACK 3D ================= */
.tech img {
  width: 60px;
  margin: 10px;
  transition: 0.3s;
}

.tech img:hover {
  transform: translateY(-10px) scale(1.2);
  filter: drop-shadow(0 10px 10px #00c9ff);
}

/* ================= PROJECT CARDS ================= */
.card {
  display: inline-block;
  width: 250px;
  margin: 15px;
  padding: 15px;
  background: #0f2027;
  border: 1px solid #00c9ff;
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
<div class="typing">Building Future Web Apps</div>

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
Currently learning the MERN stack and building interactive web applications.
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
<img src="https://skillicons.dev/icons?i=express">
<img src="https://skillicons.dev/icons?i=mongodb">
<img src="https://skillicons.dev/icons?i=git">
<img src="https://skillicons.dev/icons?i=github">
<img src="https://skillicons.dev/icons?i=vscode">
</div>

</div>

<!-- CONTACT -->
<div class="section">
<h2>Contact</h2>

<a href="https://github.com/RaniPatel16" class="btn">GitHub</a>
<a href="#" class="btn">LinkedIn</a>
<a href="#" class="btn">LeetCode</a>

</div>

</body>
</html>

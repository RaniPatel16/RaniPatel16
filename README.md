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

/* 3D HEADER */
.header {
  height: 200px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 40px;
  font-weight: bold;
  background: linear-gradient(90deg, #0f2027, #203a43, #2c5364);
  transform: perspective(800px) rotateX(15deg);
  transform-origin: top;
  animation: float 4s ease-in-out infinite;
  box-shadow: 0 20px 40px rgba(0,0,0,0.5);
}

@keyframes float {
  0%, 100% {
    transform: perspective(800px) rotateX(15deg) translateY(0);
  }
  50% {
    transform: perspective(800px) rotateX(15deg) translateY(-10px);
  }
}

.name {
  margin-top: 30px;
  font-size: 30px;
  color: #ccc;
}

.role {
  color: #00c9ff;
  font-size: 22px;
  margin-top: 10px;
  font-family: monospace;
  letter-spacing: 2px;
}

/* SECTION */
.section {
  margin: 40px 20px;
}

/* BUTTON */
.btn {
  display: inline-block;
  padding: 10px 20px;
  background: #00c9ff;
  color: black;
  text-decoration: none;
  font-weight: bold;
  border-radius: 5px;
}

/* PROJECT CARDS */
.card {
  border: 1px solid #00c9ff;
  padding: 15px;
  margin: 10px;
  display: inline-block;
  width: 250px;
  background: #0f2027;
}
</style>

</head>

<body>

<!-- 3D HEADER -->
<div class="header">Rani Patel</div>

<div class="name">Rani Patel</div>
<div class="role">MERN Stack Developer</div>

<!-- TERMINAL -->
<div class="section">
<code>
> Initializing Profile... <br>
> Loading Skills... <br>
> Access Granted ✅
</code>
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
<a href="https://your-portfolio-link.com" class="btn">Open Portfolio</a>
</div>

<!-- PROJECTS -->
<div class="section">
<h2>Projects</h2>

<div class="card">
<h3>BigBasket Clone</h3>
<p>E-commerce interface</p>
</div>

<div class="card">
<h3>Porter Clone</h3>
<p>Logistics UI</p>
</div>

<div class="card">
<h3>BBC News Clone</h3>
<p>News website</p>
</div>

<div class="card">
<h3>AI Chatbot</h3>
<p>Chat UI</p>
</div>

</div>

<!-- TECH STACK -->
<div class="section">
<h2>Technology Stack</h2>
<p>HTML • CSS • JS • React • Node • MongoDB</p>
</div>

<!-- CONTACT -->
<div class="section">
<h2>Contact</h2>

<a href="https://github.com/RaniPatel16" class="btn">GitHub</a>
<a href="https://linkedin.com/in/YOUR_LINK" class="btn">LinkedIn</a>
<a href="https://leetcode.com/YOUR_LEETCODE_USERNAME" class="btn">LeetCode</a>

</div>

</body>
</html>

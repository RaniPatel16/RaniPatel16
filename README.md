"<!DOCTYPE html>
<html lang=\"en\">
<head>
<meta charset=\"UTF-8\">
<meta name=\"viewport\" content=\"width=device-width, initial-scale=1.0\">
<title>Rani Patel - Portfolio</title>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  margin: 0;
  background: #020b12;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  color: white;
  text-align: center;
  overflow-x: hidden;
  position: relative;
}

/* PARTICLE CANVAS */
#particles-canvas {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 0;
  pointer-events: none;
}

/* CURSOR TRAIL */
.cursor-trail {
  position: fixed;
  width: 10px;
  height: 10px;
  border-radius: 50%;
  background: rgba(0, 201, 255, 0.5);
  pointer-events: none;
  z-index: 9999;
  animation: fadeOut 1s forwards;
}

@keyframes fadeOut {
  to {
    opacity: 0;
    transform: scale(2);
  }
}

/* MAIN CONTAINER */
.container {
  position: relative;
  z-index: 1;
}

/* HEADER */
.header {
  height: 250px;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  font-size: 48px;
  font-weight: bold;
  background: linear-gradient(135deg, #0f2027, #203a43, #2c5364);
  transform: perspective(1000px) rotateX(5deg);
  animation: floatHeader 6s ease-in-out infinite, colorPulse 8s ease-in-out infinite;
  position: relative;
  overflow: hidden;
  box-shadow: 0 20px 60px rgba(0, 201, 255, 0.3);
}

.header::before {
  content: '';
  position: absolute;
  top: -50%;
  left: -50%;
  width: 200%;
  height: 200%;
  background: linear-gradient(45deg, transparent, rgba(0, 201, 255, 0.1), transparent);
  animation: shine 3s linear infinite;
}

@keyframes floatHeader {
  0%, 100% { 
    transform: perspective(1000px) rotateX(5deg) translateY(0); 
  }
  50% { 
    transform: perspective(1000px) rotateX(5deg) translateY(-15px); 
  }
}

@keyframes colorPulse {
  0%, 100% { 
    filter: hue-rotate(0deg) brightness(1); 
  }
  50% { 
    filter: hue-rotate(10deg) brightness(1.2); 
  }
}

@keyframes shine {
  0% { transform: translateX(-100%) translateY(-100%) rotate(45deg); }
  100% { transform: translateX(100%) translateY(100%) rotate(45deg); }
}

.header-title {
  position: relative;
  z-index: 2;
  text-shadow: 0 0 20px rgba(0, 201, 255, 0.8),
               0 0 40px rgba(0, 201, 255, 0.6),
               0 0 60px rgba(0, 201, 255, 0.4);
  animation: glow 2s ease-in-out infinite;
}

@keyframes glow {
  0%, 100% { 
    text-shadow: 0 0 20px rgba(0, 201, 255, 0.8),
                 0 0 40px rgba(0, 201, 255, 0.6); 
  }
  50% { 
    text-shadow: 0 0 30px rgba(0, 201, 255, 1),
                 0 0 60px rgba(0, 201, 255, 0.8),
                 0 0 90px rgba(0, 201, 255, 0.6); 
  }
}

/* NAME */
.name {
  margin-top: 50px;
  font-size: 36px;
  color: #ccc;
  opacity: 0;
  animation: fadeInUp 1s ease-out 0.5s forwards;
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* TYPING */
.typing {
  font-size: 24px;
  color: #00c9ff;
  font-family: 'Courier New', monospace;
  margin-top: 15px;
  min-height: 30px;
  opacity: 0;
  animation: fadeIn 1s ease-out 1s forwards;
}

.typing::after {
  content: '|';
  animation: blink 0.8s infinite;
}

@keyframes blink {
  0%, 50% { opacity: 1; }
  51%, 100% { opacity: 0; }
}

@keyframes fadeIn {
  to { opacity: 1; }
}

/* TERMINAL */
.terminal {
  margin: 60px auto;
  max-width: 600px;
  padding: 20px;
  background: linear-gradient(135deg, #0d1b2a, #1b263b);
  border-radius: 12px;
  box-shadow: 0 0 30px rgba(0, 201, 255, 0.4);
  font-family: 'Courier New', monospace;
  text-align: left;
  border: 2px solid #00c9ff;
  opacity: 0;
  animation: fadeInUp 1s ease-out 1.5s forwards;
  position: relative;
  overflow: hidden;
}

.terminal::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(0, 201, 255, 0.2), transparent);
  animation: scanline 3s linear infinite;
}

@keyframes scanline {
  0% { left: -100%; }
  100% { left: 100%; }
}

.terminal-line {
  margin: 8px 0;
  opacity: 0;
  animation: terminalType 0.5s ease-out forwards;
}

.terminal-line:nth-child(1) { animation-delay: 2s; }
.terminal-line:nth-child(2) { animation-delay: 2.3s; }
.terminal-line:nth-child(3) { animation-delay: 2.6s; }

@keyframes terminalType {
  to { opacity: 1; }
}

/* SECTION */
.section {
  margin: 80px 20px;
  opacity: 0;
  transform: translateY(50px);
  transition: all 0.8s ease-out;
}

.section.visible {
  opacity: 1;
  transform: translateY(0);
}

.section h2 {
  font-size: 36px;
  margin-bottom: 30px;
  background: linear-gradient(90deg, #00c9ff, #92fe9d);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  display: inline-block;
  position: relative;
  animation: slideIn 0.8s ease-out;
}

.section h2::after {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 50%;
  transform: translateX(-50%);
  width: 0;
  height: 3px;
  background: linear-gradient(90deg, #00c9ff, #92fe9d);
  transition: width 0.5s ease;
}

.section.visible h2::after {
  width: 100%;
}

@keyframes slideIn {
  from {
    opacity: 0;
    transform: translateX(-50px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

/* 3D BUTTON */
.btn {
  display: inline-block;
  padding: 15px 35px;
  margin: 12px;
  color: #00c9ff;
  text-decoration: none;
  border: 2px solid #00c9ff;
  border-radius: 50px;
  transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  position: relative;
  overflow: hidden;
  font-weight: 600;
  letter-spacing: 1px;
}

.btn::before {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  width: 0;
  height: 0;
  border-radius: 50%;
  background: #00c9ff;
  transform: translate(-50%, -50%);
  transition: width 0.6s, height 0.6s;
  z-index: -1;
}

.btn:hover::before {
  width: 300px;
  height: 300px;
}

.btn:hover {
  color: #020b12;
  transform: translateY(-8px) scale(1.08);
  box-shadow: 0 15px 40px rgba(0, 201, 255, 0.6),
              0 0 30px rgba(0, 201, 255, 0.4);
  border-color: #92fe9d;
}

.btn:active {
  transform: translateY(-4px) scale(1.05);
}

/* TECH ICONS */
.tech {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 20px;
}

.tech-item {
  position: relative;
  transition: all 0.4s ease;
}

.tech img {
  width: 70px;
  height: 70px;
  transition: all 0.4s cubic-bezier(0.68, -0.55, 0.265, 1.55);
  filter: drop-shadow(0 5px 10px rgba(0, 0, 0, 0.5));
}

.tech-item:hover img {
  transform: translateY(-20px) scale(1.3) rotateY(360deg);
  filter: drop-shadow(0 20px 30px rgba(0, 201, 255, 0.8));
}

.tech-item::after {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 50%;
  transform: translateX(-50%);
  width: 0;
  height: 3px;
  background: linear-gradient(90deg, #00c9ff, #92fe9d);
  transition: width 0.4s ease;
  border-radius: 2px;
}

.tech-item:hover::after {
  width: 100%;
}

/* SKILL BARS */
.skills-container {
  max-width: 800px;
  margin: 40px auto;
  padding: 0 20px;
}

.skill-bar {
  margin: 25px 0;
  text-align: left;
}

.skill-name {
  font-size: 18px;
  margin-bottom: 8px;
  color: #00c9ff;
  font-weight: 600;
}

.skill-progress {
  width: 100%;
  height: 25px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 50px;
  overflow: hidden;
  box-shadow: inset 0 2px 5px rgba(0, 0, 0, 0.5);
}

.skill-fill {
  height: 100%;
  background: linear-gradient(90deg, #00c9ff, #92fe9d);
  border-radius: 50px;
  width: 0;
  transition: width 2s cubic-bezier(0.68, -0.55, 0.265, 1.55);
  position: relative;
  overflow: hidden;
}

.skill-fill::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.3), transparent);
  animation: shimmer 2s infinite;
}

@keyframes shimmer {
  0% { transform: translateX(-100%); }
  100% { transform: translateX(100%); }
}

.section.visible .skill-fill {
  width: var(--skill-width);
}

/* PROJECT CARDS */
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 30px;
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}

.card {
  background: linear-gradient(135deg, #0f2027, #203a43);
  border: 2px solid #00c9ff;
  border-radius: 20px;
  padding: 30px;
  transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  position: relative;
  overflow: hidden;
  cursor: pointer;
  transform-style: preserve-3d;
}

.card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, rgba(0, 201, 255, 0.1), rgba(146, 254, 157, 0.1));
  opacity: 0;
  transition: opacity 0.5s;
}

.card:hover::before {
  opacity: 1;
}

.card:hover {
  transform: translateY(-20px) scale(1.05) rotateX(5deg);
  box-shadow: 0 20px 60px rgba(0, 201, 255, 0.6),
              0 0 50px rgba(146, 254, 157, 0.4);
  border-color: #92fe9d;
}

.card-title {
  font-size: 22px;
  font-weight: bold;
  color: #00c9ff;
  margin-bottom: 10px;
  transition: all 0.3s;
}

.card:hover .card-title {
  color: #92fe9d;
  transform: scale(1.1);
}

.card-icon {
  font-size: 48px;
  margin-bottom: 15px;
  animation: bounce 2s infinite;
}

@keyframes bounce {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-10px); }
}

/* ABOUT TEXT */
.about-text {
  max-width: 800px;
  margin: 0 auto;
  padding: 30px;
  line-height: 1.8;
  font-size: 18px;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 15px;
  border: 1px solid rgba(0, 201, 255, 0.3);
  backdrop-filter: blur(10px);
}

/* WAVE ANIMATION */
.wave-container {
  position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 150px;
  z-index: -1;
  overflow: hidden;
}

.wave {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 200%;
  height: 100%;
  background: url(\"data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 1200 120' preserveAspectRatio='none'%3E%3Cpath d='M321.39,56.44c58-10.79,114.16-30.13,172-41.86,82.39-16.72,168.19-17.73,250.45-.39C823.78,31,906.67,72,985.66,92.83c70.05,18.48,146.53,26.09,214.34,3V0H0V27.35A600.21,600.21,0,0,0,321.39,56.44Z' fill='rgba(0,201,255,0.1)'/%3E%3C/svg%3E\");
  background-size: 50% 100%;
  animation: wave 15s linear infinite;
}

.wave:nth-child(2) {
  animation: wave 20s linear infinite reverse;
  opacity: 0.5;
}

@keyframes wave {
  0% { transform: translateX(0); }
  100% { transform: translateX(-50%); }
}

/* FLOATING ELEMENTS */
.floating-icon {
  position: fixed;
  font-size: 40px;
  opacity: 0.3;
  animation: float-random 20s infinite ease-in-out;
  z-index: 0;
  pointer-events: none;
}

.floating-icon:nth-child(1) { top: 10%; left: 10%; animation-delay: 0s; }
.floating-icon:nth-child(2) { top: 20%; right: 15%; animation-delay: 3s; }
.floating-icon:nth-child(3) { top: 60%; left: 5%; animation-delay: 6s; }
.floating-icon:nth-child(4) { top: 80%; right: 10%; animation-delay: 9s; }

@keyframes float-random {
  0%, 100% { transform: translate(0, 0) rotate(0deg); }
  25% { transform: translate(30px, -30px) rotate(90deg); }
  50% { transform: translate(-20px, 20px) rotate(180deg); }
  75% { transform: translate(40px, 30px) rotate(270deg); }
}

/* SCROLL INDICATOR */
.scroll-indicator {
  position: fixed;
  bottom: 30px;
  left: 50%;
  transform: translateX(-50%);
  animation: scrollBounce 2s infinite;
  z-index: 100;
  cursor: pointer;
}

.scroll-indicator::before {
  content: '↓';
  font-size: 36px;
  color: #00c9ff;
  text-shadow: 0 0 20px rgba(0, 201, 255, 0.8);
}

@keyframes scrollBounce {
  0%, 100% { transform: translateX(-50%) translateY(0); }
  50% { transform: translateX(-50%) translateY(-15px); }
}

/* RESPONSIVE */
@media (max-width: 768px) {
  .header {
    font-size: 32px;
    height: 180px;
  }
  
  .name {
    font-size: 28px;
  }
  
  .typing {
    font-size: 18px;
  }
  
  .section h2 {
    font-size: 28px;
  }
  
  .tech img {
    width: 50px;
    height: 50px;
  }
  
  .projects-grid {
    grid-template-columns: 1fr;
  }
  
  .btn {
    padding: 12px 25px;
    font-size: 14px;
  }
}

/* LOADING ANIMATION */
.loading-screen {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: #020b12;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 10000;
  animation: fadeOutLoading 1s ease-out 2s forwards;
}

.loader {
  width: 80px;
  height: 80px;
  border: 6px solid rgba(0, 201, 255, 0.2);
  border-top: 6px solid #00c9ff;
  border-radius: 50%;
  animation: spin 1s linear infinite;
}

@keyframes spin {
  to { transform: rotate(360deg); }
}

@keyframes fadeOutLoading {
  to {
    opacity: 0;
    visibility: hidden;
  }
}
</style>

</head>

<body>

<!-- LOADING SCREEN -->
<div class=\"loading-screen\">
  <div class=\"loader\"></div>
</div>

<!-- PARTICLE CANVAS -->
<canvas id=\"particles-canvas\"></canvas>

<!-- WAVE BACKGROUND -->
<div class=\"wave-container\">
  <div class=\"wave\"></div>
  <div class=\"wave\"></div>
</div>

<!-- FLOATING ICONS -->
<div class=\"floating-icon\">💻</div>
<div class=\"floating-icon\">⚡</div>
<div class=\"floating-icon\">🚀</div>
<div class=\"floating-icon\">✨</div>

<div class=\"container\">

<!-- HEADER -->
<div class=\"header\">
  <div class=\"header-title\">Rani Patel</div>
</div>

<div class=\"name\">Rani Patel</div>
<div class=\"typing\" id=\"typing\"></div>

<!-- TERMINAL -->
<div class=\"terminal\">
  <div class=\"terminal-line\">> Initializing Profile...</div>
  <div class=\"terminal-line\">> Loading Skills...</div>
  <div class=\"terminal-line\">> Access Granted ✅</div>
</div>

<!-- ABOUT -->
<div class=\"section\">
  <h2>About Me</h2>
  <div class=\"about-text\">
    Frontend developer focused on building modern web interfaces and exploring AI-driven solutions.
    <br><br>
    Currently learning the MERN stack and building interactive web applications with passion and creativity.
    <br><br>
    Always eager to learn new technologies and solve challenging problems.
  </div>
</div>

<!-- PORTFOLIO -->
<div class=\"section\">
  <h2>Portfolio</h2>
  <a href=\"#\" class=\"btn\">Open Portfolio</a>
</div>

<!-- PROJECTS -->
<div class=\"section\">
  <h2>Projects</h2>
  
  <div class=\"projects-grid\">
    <div class=\"card\">
      <div class=\"card-icon\">🛒</div>
      <div class=\"card-title\">BigBasket Clone</div>
      <p>E-commerce platform with modern UI</p>
    </div>
    
    <div class=\"card\">
      <div class=\"card-icon\">🚚</div>
      <div class=\"card-title\">Porter Clone</div>
      <p>Logistics and delivery service app</p>
    </div>
    
    <div class=\"card\">
      <div class=\"card-icon\">📰</div>
      <div class=\"card-title\">BBC News Clone</div>
      <p>News aggregation platform</p>
    </div>
    
    <div class=\"card\">
      <div class=\"card-icon\">🤖</div>
      <div class=\"card-title\">AI Chatbot</div>
      <p>Intelligent conversational AI</p>
    </div>
  </div>
</div>

<!-- SKILLS WITH PROGRESS BARS -->
<div class=\"section\">
  <h2>Skills & Proficiency</h2>
  
  <div class=\"skills-container\">
    <div class=\"skill-bar\">
      <div class=\"skill-name\">HTML & CSS</div>
      <div class=\"skill-progress\">
        <div class=\"skill-fill\" style=\"--skill-width: 90%\"></div>
      </div>
    </div>
    
    <div class=\"skill-bar\">
      <div class=\"skill-name\">JavaScript</div>
      <div class=\"skill-progress\">
        <div class=\"skill-fill\" style=\"--skill-width: 85%\"></div>
      </div>
    </div>
    
    <div class=\"skill-bar\">
      <div class=\"skill-name\">React.js</div>
      <div class=\"skill-progress\">
        <div class=\"skill-fill\" style=\"--skill-width: 80%\"></div>
      </div>
    </div>
    
    <div class=\"skill-bar\">
      <div class=\"skill-name\">Node.js & Express</div>
      <div class=\"skill-progress\">
        <div class=\"skill-fill\" style=\"--skill-width: 75%\"></div>
      </div>
    </div>
    
    <div class=\"skill-bar\">
      <div class=\"skill-name\">MongoDB</div>
      <div class=\"skill-progress\">
        <div class=\"skill-fill\" style=\"--skill-width: 70%\"></div>
      </div>
    </div>
  </div>
</div>

<!-- TECH STACK -->
<div class=\"section\">
  <h2>Technology Stack</h2>
  
  <div class=\"tech\">
    <div class=\"tech-item\">
      <img src=\"https://skillicons.dev/icons?i=html\" alt=\"HTML\">
    </div>
    <div class=\"tech-item\">
      <img src=\"https://skillicons.dev/icons?i=css\" alt=\"CSS\">
    </div>
    <div class=\"tech-item\">
      <img src=\"https://skillicons.dev/icons?i=js\" alt=\"JavaScript\">
    </div>
    <div class=\"tech-item\">
      <img src=\"https://skillicons.dev/icons?i=react\" alt=\"React\">
    </div>
    <div class=\"tech-item\">
      <img src=\"https://skillicons.dev/icons?i=nodejs\" alt=\"Node.js\">
    </div>
    <div class=\"tech-item\">
      <img src=\"https://skillicons.dev/icons?i=express\" alt=\"Express\">
    </div>
    <div class=\"tech-item\">
      <img src=\"https://skillicons.dev/icons?i=mongodb\" alt=\"MongoDB\">
    </div>
    <div class=\"tech-item\">
      <img src=\"https://skillicons.dev/icons?i=git\" alt=\"Git\">
    </div>
    <div class=\"tech-item\">
      <img src=\"https://skillicons.dev/icons?i=github\" alt=\"GitHub\">
    </div>
    <div class=\"tech-item\">
      <img src=\"https://skillicons.dev/icons?i=vscode\" alt=\"VS Code\">
    </div>
  </div>
</div>

<!-- CONTACT -->
<div class=\"section\">
  <h2>Let's Connect</h2>
  
  <a href=\"https://github.com/RaniPatel16\" class=\"btn\" target=\"_blank\">GitHub</a>
  <a href=\"#\" class=\"btn\">LinkedIn</a>
  <a href=\"#\" class=\"btn\">LeetCode</a>
</div>

<div style=\"height: 100px;\"></div>

</div>

<!-- SCROLL INDICATOR -->
<div class=\"scroll-indicator\" onclick=\"window.scrollTo({top: 0, behavior: 'smooth'})\"></div>

<!-- JAVASCRIPT -->
<script>
// ============ TYPING ANIMATION ============
const text = \"Building Future Web Apps 🚀\";
let i = 0;
const speed = 100;

function type() {
  if (i < text.length) {
    document.getElementById(\"typing\").innerHTML = text.substring(0, i + 1);
    i++;
    setTimeout(type, speed);
  }
}

setTimeout(type, 1500);

// ============ PARTICLE ANIMATION ============
const canvas = document.getElementById('particles-canvas');
const ctx = canvas.getContext('2d');

canvas.width = window.innerWidth;
canvas.height = window.innerHeight;

class Particle {
  constructor() {
    this.x = Math.random() * canvas.width;
    this.y = Math.random() * canvas.height;
    this.vx = (Math.random() - 0.5) * 0.5;
    this.vy = (Math.random() - 0.5) * 0.5;
    this.size = Math.random() * 2 + 1;
  }

  update() {
    this.x += this.vx;
    this.y += this.vy;

    if (this.x < 0 || this.x > canvas.width) this.vx *= -1;
    if (this.y < 0 || this.y > canvas.height) this.vy *= -1;
  }

  draw() {
    ctx.fillStyle = 'rgba(0, 201, 255, 0.5)';
    ctx.beginPath();
    ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
    ctx.fill();
  }
}

const particles = [];
for (let i = 0; i < 100; i++) {
  particles.push(new Particle());
}

function animateParticles() {
  ctx.clearRect(0, 0, canvas.width, canvas.height);
  
  particles.forEach((particle, i) => {
    particle.update();
    particle.draw();
    
    // Draw connections
    particles.forEach((otherParticle, j) => {
      if (i !== j) {
        const dx = particle.x - otherParticle.x;
        const dy = particle.y - otherParticle.y;
        const distance = Math.sqrt(dx * dx + dy * dy);
        
        if (distance < 100) {
          ctx.strokeStyle = `rgba(0, 201, 255, ${0.2 - distance / 500})`;
          ctx.lineWidth = 0.5;
          ctx.beginPath();
          ctx.moveTo(particle.x, particle.y);
          ctx.lineTo(otherParticle.x, otherParticle.y);
          ctx.stroke();
        }
      }
    });
  });
  
  requestAnimationFrame(animateParticles);
}

animateParticles();

// ============ RESIZE HANDLER ============
window.addEventListener('resize', () => {
  canvas.width = window.innerWidth;
  canvas.height = window.innerHeight;
});

// ============ SCROLL REVEAL ANIMATION ============
const observerOptions = {
  threshold: 0.1,
  rootMargin: '0px 0px -100px 0px'
};

const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('visible');
    }
  });
}, observerOptions);

document.querySelectorAll('.section').forEach(section => {
  observer.observe(section);
});

// ============ CURSOR TRAIL EFFECT ============
let trails = [];
document.addEventListener('mousemove', (e) => {
  const trail = document.createElement('div');
  trail.className = 'cursor-trail';
  trail.style.left = e.pageX + 'px';
  trail.style.top = e.pageY + 'px';
  document.body.appendChild(trail);
  
  trails.push(trail);
  
  setTimeout(() => {
    trail.remove();
    trails = trails.filter(t => t !== trail);
  }, 1000);
  
  // Limit trail elements
  if (trails.length > 20) {
    const oldTrail = trails.shift();
    if (oldTrail) oldTrail.remove();
  }
});

// ============ HIDE SCROLL INDICATOR ON SCROLL ============
let scrollTimeout;
const scrollIndicator = document.querySelector('.scroll-indicator');

window.addEventListener('scroll', () => {
  if (window.scrollY > 200) {
    scrollIndicator.style.opacity = '1';
    scrollIndicator.querySelector('::before') ? null : null;
  } else {
    scrollIndicator.style.opacity = '0.5';
  }
});

// ============ SMOOTH SCROLL FOR ALL LINKS ============
document.querySelectorAll('a[href^=\"#\"]').forEach(anchor => {
  anchor.addEventListener('click', function (e) {
    e.preventDefault();
    const target = document.querySelector(this.getAttribute('href'));
    if (target) {
      target.scrollIntoView({
        behavior: 'smooth',
        block: 'start'
      });
    }
  });
});

// ============ 3D CARD TILT EFFECT ============
document.querySelectorAll('.card').forEach(card => {
  card.addEventListener('mousemove', (e) => {
    const rect = card.getBoundingClientRect();
    const x = e.clientX - rect.left;
    const y = e.clientY - rect.top;
    
    const centerX = rect.width / 2;
    const centerY = rect.height / 2;
    
    const rotateX = (y - centerY) / 10;
    const rotateY = (centerX - x) / 10;
    
    card.style.transform = `translateY(-20px) scale(1.05) rotateX(${rotateX}deg) rotateY(${rotateY}deg)`;
  });
  
  card.addEventListener('mouseleave', () => {
    card.style.transform = '';
  });
});

// ============ PARALLAX EFFECT ON SCROLL ============
window.addEventListener('scroll', () => {
  const scrolled = window.pageYOffset;
  const parallaxElements = document.querySelectorAll('.header, .floating-icon');
  
  parallaxElements.forEach((el, index) => {
    const speed = 0.5 + (index * 0.1);
    el.style.transform = `translateY(${scrolled * speed}px)`;
  });
});

console.log('%c👋 Welcome to Rani Patel's Portfolio!', 'color: #00c9ff; font-size: 20px; font-weight: bold;');
console.log('%c🚀 Built with passion and creativity', 'color: #92fe9d; font-size: 14px;');
</script>

</body>
</html>
"

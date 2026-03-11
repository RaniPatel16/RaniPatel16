<!DOCTYPE html>
<html lang="en">

<head>

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Rani Patel | Developer Portfolio</title>

<link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;600;700&display=swap" rel="stylesheet">

<link rel="stylesheet"
href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

<style>

body{
font-family:'Outfit',sans-serif;
background:#050507;
color:white;
margin:0;
}

section{
padding:100px 0;
text-align:center;
}

/* COOL BANNER */

.banner{
background:linear-gradient(90deg,#8c52ff,#00d2ff);
padding:40px;
font-size:32px;
font-weight:700;
}

/* HERO */

.hero{
height:80vh;
display:flex;
flex-direction:column;
justify-content:center;
align-items:center;
}

.hero h1{
font-size:70px;
}

.typing{
color:#00d2ff;
font-size:26px;
margin-bottom:20px;
}

/* TECH STACK */

.tech-sphere{
width:300px;
height:300px;
margin:auto;
position:relative;
transform-style:preserve-3d;
animation:rotateSphere 20s linear infinite;
}

.tech-item{
position:absolute;
font-size:40px;
left:50%;
top:50%;
}

@keyframes rotateSphere{
from{transform:rotateY(0deg);}
to{transform:rotateY(360deg);}
}

/* PROJECTS */

.projects{
display:flex;
flex-wrap:wrap;
justify-content:center;
}

.project-card{
width:280px;
height:180px;
background:#111;
border-radius:10px;
margin:20px;
display:flex;
align-items:center;
justify-content:center;
transition:0.4s;
font-size:18px;
}

.project-card:hover{
transform:rotateY(15deg) rotateX(10deg) scale(1.05);
}

/* PORTFOLIO PREVIEW */

.preview img{
width:70%;
border-radius:12px;
}

/* GITHUB */

.github img{
max-width:90%;
margin:10px;
}

/* VISITOR COUNTER */

.counter{
margin-top:20px;
}

/* CHATBOT */

#chatbot{
position:fixed;
bottom:20px;
right:20px;
width:260px;
background:#111;
border-radius:10px;
overflow:hidden;
}

#chat-header{
background:#8c52ff;
padding:10px;
text-align:center;
}

#chat-body{
height:180px;
overflow:auto;
padding:10px;
font-size:14px;
}

#chat-input{
width:100%;
padding:10px;
border:none;
background:#000;
color:white;
}

</style>

</head>

<body>

<!-- COOL BANNER -->

<div class="banner">
🚀 Welcome to My Developer Portfolio
</div>

<!-- HERO -->

<section class="hero">

<h1>Rani Patel</h1>

<div class="typing">
<span id="typing"></span>
</div>

</section>

<!-- TECH STACK -->

<section>

<h2>3D Tech Stack</h2>

<div class="tech-sphere">

<div class="tech-item"><i class="fab fa-html5"></i></div>
<div class="tech-item"><i class="fab fa-css3-alt"></i></div>
<div class="tech-item"><i class="fab fa-js"></i></div>
<div class="tech-item"><i class="fab fa-react"></i></div>
<div class="tech-item"><i class="fab fa-node-js"></i></div>
<div class="tech-item"><i class="fab fa-git-alt"></i></div>
<div class="tech-item"><i class="fab fa-github"></i></div>

</div>

</section>

<!-- PROJECTS -->

<section>

<h2>Projects</h2>

<div class="projects">

<div class="project-card">BigBasket Clone</div>
<div class="project-card">Porter Clone</div>
<div class="project-card">BBC News Clone</div>
<div class="project-card">AI Chatbot</div>

</div>

</section>

<!-- PORTFOLIO PREVIEW -->

<section class="preview">

<h2>Portfolio Preview</h2>

<img src="https://via.placeholder.com/900x450.png?text=Portfolio+Preview">

</section>

<!-- GITHUB STATS -->

<section class="github">

<h2>GitHub Stats</h2>

<img src="https://github-readme-stats.vercel.app/api?username=RaniPatel16&show_icons=true&theme=tokyonight">

<img src="https://github-readme-streak-stats.herokuapp.com/?user=RaniPatel16&theme=tokyonight">

<img src="https://github-profile-trophy.vercel.app/?username=RaniPatel16&theme=tokyonight">

<img src="https://github-readme-activity-graph.vercel.app/graph?username=RaniPatel16&theme=tokyo-night">

<img src="https://raw.githubusercontent.com/Platane/snk/output/github-contribution-grid-snake.svg">

</section>

<!-- VISITOR COUNTER -->

<section class="counter">

<h2>Visitor Counter</h2>

<img src="https://komarev.com/ghpvc/?username=RaniPatel16&label=Profile%20Views&color=blue&style=flat">

</section>

<!-- CONTACT -->

<section>

<h2>Contact</h2>

<p><a href="https://www.linkedin.com" style="color:#00d2ff;">LinkedIn</a></p>
<p><a href="https://github.com/RaniPatel16" style="color:#00d2ff;">GitHub</a></p>
<p>Phone: 9898225910</p>

</section>

<!-- AI CHATBOT -->

<div id="chatbot">

<div id="chat-header">AI Assistant</div>

<div id="chat-body"></div>

<input id="chat-input" placeholder="Ask about Rani">

</div>

<script>

/* TYPING HEADER */

const words=["Frontend Developer","UI Designer","React Developer","Creative Coder"];

let i=0;
let j=0;
let deleting=false;

function type(){

let word=words[i];

document.getElementById("typing").innerText=
deleting?word.substring(0,j--):word.substring(0,j++);

if(!deleting && j===word.length){
deleting=true;
setTimeout(type,1000);
return;
}

if(deleting && j===0){
deleting=false;
i=(i+1)%words.length;
}

setTimeout(type,deleting?40:80);

}

type();

</script>

</body>
</html>

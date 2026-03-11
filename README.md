<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rani Patel | Developer Portfolio</title>
    
    <!-- Fonts & Icons -->
    <link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <!-- GSAP -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/ScrollTrigger.min.js"></script>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Outfit', sans-serif;
            background: #050507;
            color: white;
            line-height: 1.6;
            overflow-x: hidden;
        }

        section {
            padding: 80px 0;
            text-align: center;
        }

        .container {
            width: 90%;
            max-width: 1100px;
            margin: auto;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            position: relative;
            overflow: hidden;
        }

        .hero h1 {
            font-size: clamp(40px, 8vw, 70px);
            margin-bottom: 20px;
            background: linear-gradient(135deg, #8c52ff, #00d2ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: glow 3s ease-in-out infinite;
        }

        @keyframes glow {
            0%, 100% { filter: drop-shadow(0 0 20px rgba(140, 82, 255, 0.3)); }
            50% { filter: drop-shadow(0 0 30px rgba(0, 210, 255, 0.5)); }
        }

        .typing {
            color: #00d2ff;
            font-size: 24px;
            margin-bottom: 30px;
            min-height: 40px;
        }

        /* 3D Tech Sphere */
        .tech-sphere {
            width: 300px;
            height: 300px;
            margin: 50px auto;
            position: relative;
            transform-style: preserve-3d;
            animation: rotateSphere 20s linear infinite;
        }

        .tech-item {
            position: absolute;
            font-size: 40px;
            left: 50%;
            top: 50%;
            transform-style: preserve-3d;
            color: #00d2ff;
            text-shadow: 0 0 10px rgba(0, 210, 255, 0.5);
            transition: all 0.3s ease;
        }

        .tech-item:hover {
            color: #8c52ff;
            transform: scale(1.2) translateZ(50px);
            text-shadow: 0 0 20px rgba(140, 82, 255, 0.8);
        }

        @keyframes rotateSphere {
            0% { transform: rotateY(0deg) rotateX(10deg); }
            100% { transform: rotateY(360deg) rotateX(10deg); }
        }

        /* Position tech items in a sphere */
        .tech-item:nth-child(1) { transform: translateX(-50%) translateY(-50%) rotateY(0deg) translateZ(150px); }
        .tech-item:nth-child(2) { transform: translateX(-50%) translateY(-50%) rotateY(60deg) translateZ(150px); }
        .tech-item:nth-child(3) { transform: translateX(-50%) translateY(-50%) rotateY(120deg) translateZ(150px); }
        .tech-item:nth-child(4) { transform: translateX(-50%) translateY(-50%) rotateY(180deg) translateZ(150px); }
        .tech-item:nth-child(5) { transform: translateX(-50%) translateY(-50%) rotateY(240deg) translateZ(150px); }
        .tech-item:nth-child(6) { transform: translateX(-50%) translateY(-50%) rotateY(300deg) translateZ(150px); }
        .tech-item:nth-child(7) { transform: translateX(-50%) translateY(-50%) rotateX(90deg) translateZ(150px); }

        /* Projects */
        .projects {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 30px;
            padding: 20px;
        }

        .project-card {
            width: 280px;
            height: 180px;
            background: linear-gradient(145deg, #1a1a1a, #111);
            border-radius: 15px;
            margin: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            cursor: pointer;
            border: 1px solid rgba(140, 82, 255, 0.2);
            position: relative;
            overflow: hidden;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.1), transparent);
            transition: left 0.5s ease;
        }

        .project-card:hover::before {
            left: 100%;
        }

        .project-card:hover {
            transform: rotateY(10deg) rotateX(5deg) scale(1.05);
            box-shadow: 0 20px 30px rgba(140, 82, 255, 0.3);
            border-color: #8c52ff;
        }

        /* GitHub section */
        .github {
            background: linear-gradient(180deg, #050507 0%, #0a0a0f 100%);
        }

        .github-stats {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
            margin: 30px 0;
        }

        .github img {
            max-width: 100%;
            margin: 10px;
            border-radius: 10px;
            transition: transform 0.3s ease;
            border: 2px solid rgba(140, 82, 255, 0.3);
        }

        .github img:hover {
            transform: scale(1.02);
            border-color: #8c52ff;
        }

        .snake-container {
            margin: 40px auto;
            max-width: 800px;
            background: rgba(255,255,255,0.02);
            border-radius: 20px;
            padding: 20px;
        }

        /* Contact Section */
        .contact-info {
            display: flex;
            justify-content: center;
            gap: 50px;
            flex-wrap: wrap;
            margin-top: 30px;
        }

        .contact-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 10px;
            padding: 20px;
            background: rgba(255,255,255,0.03);
            border-radius: 15px;
            min-width: 200px;
            transition: all 0.3s ease;
            border: 1px solid rgba(140, 82, 255, 0.2);
        }

        .contact-item:hover {
            transform: translateY(-5px);
            background: rgba(140, 82, 255, 0.1);
            border-color: #8c52ff;
        }

        .contact-item i {
            font-size: 30px;
            color: #00d2ff;
        }

        .contact-item p {
            margin: 0;
            font-size: 16px;
        }

        /* Chatbot */
        #chatbot {
            position: fixed;
            bottom: 20px;
            right: 20px;
            width: 300px;
            background: #1a1a1a;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 40px rgba(0,0,0,0.5);
            border: 1px solid rgba(140, 82, 255, 0.3);
            z-index: 1000;
            transition: transform 0.3s ease;
        }

        #chatbot:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 50px rgba(140, 82, 255, 0.3);
        }

        #chat-header {
            background: linear-gradient(135deg, #8c52ff, #00d2ff);
            padding: 15px;
            text-align: center;
            font-weight: 600;
            font-size: 16px;
            cursor: pointer;
        }

        #chat-body {
            height: 200px;
            overflow-y: auto;
            padding: 15px;
            font-size: 14px;
            background: #111;
        }

        #chat-body p {
            margin: 8px 0;
            padding: 5px 10px;
            border-radius: 10px;
        }

        #chat-body p:first-child {
            background: rgba(140, 82, 255, 0.1);
        }

        #chat-body p:last-child {
            background: rgba(0, 210, 255, 0.1);
        }

        #chat-input {
            width: 100%;
            padding: 15px;
            border: none;
            background: #222;
            color: white;
            font-size: 14px;
            border-top: 1px solid rgba(255,255,255,0.1);
        }

        #chat-input:focus {
            outline: none;
            background: #2a2a2a;
        }

        #chat-input::placeholder {
            color: #666;
        }

        /* Section Headers */
        h2 {
            font-size: 36px;
            margin-bottom: 40px;
            background: linear-gradient(135deg, #8c52ff, #00d2ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            display: inline-block;
            position: relative;
        }

        h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 50px;
            height: 3px;
            background: linear-gradient(90deg, #8c52ff, #00d2ff);
            border-radius: 3px;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            section {
                padding: 60px 0;
            }
            
            h2 {
                font-size: 28px;
            }
            
            .tech-sphere {
                width: 250px;
                height: 250px;
            }
            
            .tech-item {
                font-size: 30px;
            }
            
            #chatbot {
                width: 280px;
                bottom: 10px;
                right: 10px;
            }
            
            .contact-info {
                gap: 20px;
            }
            
            .contact-item {
                min-width: 150px;
                padding: 15px;
            }
        }

        /* Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }

        ::-webkit-scrollbar-track {
            background: #111;
        }

        ::-webkit-scrollbar-thumb {
            background: linear-gradient(135deg, #8c52ff, #00d2ff);
            border-radius: 4px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: linear-gradient(135deg, #00d2ff, #8c52ff);
        }
    </style>
</head>

<body>
    <!-- HERO SECTION -->
    <section class="hero">
        <h1>Rani Patel</h1>
        <div class="typing">
            <span id="typing"></span>
        </div>
        <img src="https://capsule-render.vercel.app/api?type=waving&color=0:8c52ff,100:00d2ff&height=200&section=header&text=Creative%20Developer&fontSize=40&fontColor=white&animation=twinkling" 
             alt="Creative Developer Banner"
             style="max-width: 100%;">
    </section>

    <!-- TECH STACK SECTION -->
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

    <!-- PROJECTS SECTION -->
    <section>
        <h2>Projects</h2>
        <div class="projects">
            <div class="project-card">BigBasket Clone</div>
            <div class="project-card">Porter Clone</div>
            <div class="project-card">BBC News Clone</div>
            <div class="project-card">AI Chatbot</div>
        </div>
    </section>

    <!-- GITHUB STATS SECTION -->
    <section class="github">
        <h2>GitHub Stats</h2>
        <div class="github-stats">
            <img src="https://github-readme-stats.vercel.app/api?username=RaniPatel16&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0D1117" 
                 alt="GitHub Stats">
            <img src="https://github-readme-streak-stats.herokuapp.com/?user=RaniPatel16&theme=tokyonight&hide_border=true&background=0D1117" 
                 alt="GitHub Streak">
        </div>
        <div>
            <img src="https://github-profile-trophy.vercel.app/?username=RaniPatel16&theme=tokyonight&no-frame=true&no-bg=true&margin-w=15" 
                 alt="GitHub Trophies"
                 style="max-width: 100%;">
        </div>
        <div>
            <img src="https://github-readme-activity-graph.vercel.app/graph?username=RaniPatel16&theme=tokyo-night&hide_border=true&bg_color=0D1117&area=true" 
                 alt="GitHub Activity Graph"
                 style="max-width: 100%;">
        </div>
        <div class="snake-container">
            <img src="https://raw.githubusercontent.com/Platane/snk/output/github-contribution-grid-snake.svg" 
                 alt="GitHub Snake Game"
                 style="max-width: 100%; filter: invert(0.9);">
        </div>
    </section>

    <!-- CONTACT SECTION -->
    <section>
        <h2>Contact</h2>
        <div class="contact-info">
            <div class="contact-item">
                <i class="fab fa-linkedin"></i>
                <p>linkedin.com/in/ranipatel</p>
            </div>
            <div class="contact-item">
                <i class="fab fa-github"></i>
                <p>github.com/RaniPatel16</p>
            </div>
            <div class="contact-item">
                <i class="fas fa-phone"></i>
                <p>9898225910</p>
            </div>
        </div>
    </section>

    <!-- AI CHATBOT -->
    <div id="chatbot">
        <div id="chat-header">
            <i class="fas fa-robot" style="margin-right: 8px;"></i>
            AI Assistant
        </div>
        <div id="chat-body"></div>
        <input id="chat-input" type="text" placeholder="Ask about Rani...">
    </div>

    <script>
        // Typing Animation
        const words = ["Frontend Developer", "UI Designer", "React Developer", "Creative Coder"];
        let i = 0;
        let j = 0;
        let deleting = false;
        const typingElement = document.getElementById("typing");

        function type() {
            if (!typingElement) return;
            
            let word = words[i];
            
            if (deleting) {
                typingElement.innerText = word.substring(0, j--);
            } else {
                typingElement.innerText = word.substring(0, j++);
            }

            if (!deleting && j === word.length) {
                deleting = true;
                setTimeout(type, 1500);
                return;
            }

            if (deleting && j === 0) {
                deleting = false;
                i = (i + 1) % words.length;
            }

            setTimeout(type, deleting ? 40 : 100);
        }

        // Start typing animation
        type();

        // Chatbot functionality
        const chatInput = document.getElementById("chat-input");
        const chatBody = document.getElementById("chat-body");

        if (chatInput && chatBody) {
            // Add welcome message
            setTimeout(() => {
                chatBody.innerHTML += "<p><b>AI:</b> 👋 Hi! Ask me about Rani's skills or projects!</p>";
            }, 500);

            chatInput.addEventListener("keypress", function(e) {
                if (e.key === "Enter" && this.value.trim() !== "") {
                    let text = this.value.trim();
                    
                    // Add user message
                    chatBody.innerHTML += "<p><b>You:</b> " + text + "</p>";
                    
                    // Generate AI response
                    let reply = "I'm here to help! You can ask about skills, projects, or contact information.";
                    
                    if (text.toLowerCase().includes("skill") || text.toLowerCase().includes("tech")) {
                        reply = "Rani is skilled in HTML, CSS, JavaScript, React, Node.js, and MongoDB. She loves building creative web applications!";
                    } else if (text.toLowerCase().includes("project")) {
                        reply = "Rani has built several projects including BigBasket Clone, Porter Clone, BBC News Clone, and an AI Chatbot application.";
                    } else if (text.toLowerCase().includes("contact")) {
                        reply = "You can connect with Rani via LinkedIn, GitHub, or call at 9898225910.";
                    } else if (text.toLowerCase().includes("experience")) {
                        reply = "Rani has experience in frontend development, UI design, and creative coding with modern frameworks.";
                    } else if (text.includes("hi") || text.includes("hello")) {
                        reply = "Hello! 👋 How can I help you learn about Rani's portfolio?";
                    }
                    
                    // Add AI response
                    chatBody.innerHTML += "<p><b>AI:</b> " + reply + "</p>";
                    
                    // Clear input
                    this.value = "";
                    
                    // Scroll to bottom
                    chatBody.scrollTop = chatBody.scrollHeight;
                }
            });
        }

        // GSAP Animations
        gsap.registerPlugin(ScrollTrigger);

        // Animate sections on scroll
        gsap.utils.toArray('section').forEach(section => {
            gsap.from(section, {
                scrollTrigger: {
                    trigger: section,
                    start: "top 80%",
                    end: "bottom 20%",
                    toggleActions: "play none none reverse"
                },
                opacity: 0,
                y: 50,
                duration: 1,
                ease: "power2.out"
            });
        });

        // Animate project cards
        gsap.from('.project-card', {
            scrollTrigger: {
                trigger: '.projects',
                start: "top 80%",
            },
            scale: 0.8,
            opacity: 0,
            duration: 0.8,
            stagger: 0.2,
            ease: "back.out(1.2)"
        });

        // Animate GitHub stats
        gsap.from('.github img', {
            scrollTrigger: {
                trigger: '.github',
                start: "top 80%",
            },
            scale: 0.9,
            opacity: 0,
            duration: 0.8,
            stagger: 0.1,
            ease: "power2.out"
        });

        // Update tech sphere positions on resize
        window.addEventListener('resize', function() {
            const sphere = document.querySelector('.tech-sphere');
            if (sphere) {
                sphere.style.animation = 'none';
                sphere.offsetHeight; // Trigger reflow
                sphere.style.animation = 'rotateSphere 20s linear infinite';
            }
        });
    </script>
</body>

</html>

1  <!DOCTYPE html>
2  <html lang="en">
3
4  <head>
5
6  <meta charset="UTF-8">
7  <meta name="viewport" content="width=device-width, initial-scale=1.0">
8
9  <title>Rani Patel | Developer Portfolio</title>
10
11 <link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;600;700&display=swap" rel="stylesheet">
12
13 <link rel="stylesheet"
14 href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
15
16 <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
17 <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/ScrollTrigger.min.js"></script>
18
19 <style>
20
21 body{
22 font-family:'Outfit',sans-serif;
23 background:#050507;
24 color:white;
25 margin:0;
26 }
27
28 section{
29 padding:100px 0;
30 text-align:center;
31 }
32
33 .hero{
34 height:100vh;
35 display:flex;
36 flex-direction:column;
37 justify-content:center;
38 align-items:center;
39 }
40
41 .hero h1{
42 font-size:70px;
43 }
44
45 .typing{
46 color:#00d2ff;
47 font-size:24px;
48 margin-bottom:20px;
49 }
50
51 .tech-sphere{
52 width:300px;
53 height:300px;
54 margin:auto;
55 position:relative;
56 transform-style:preserve-3d;
57 animation:rotateSphere 20s linear infinite;
58 }
59
60 .tech-item{
61 position:absolute;
62 font-size:40px;
63 left:50%;
64 top:50%;
65 }
66
67 @keyframes rotateSphere{
68 from{transform:rotateY(0deg);}
69 to{transform:rotateY(360deg);}
70 }
71
72 .projects{
73 display:flex;
74 flex-wrap:wrap;
75 justify-content:center;
76 }
77
78 .project-card{
79 width:280px;
80 height:180px;
81 background:#111;
82 border-radius:10px;
83 margin:20px;
84 display:flex;
85 align-items:center;
86 justify-content:center;
87 transition:0.4s;
88 }
89
90 .project-card:hover{
91 transform:rotateY(15deg) rotateX(10deg) scale(1.05);
92 }
93
94 .github img{
95 max-width:100%;
96 margin:10px;
97 }
98
99 #chatbot{
100 position:fixed;
101 bottom:20px;
102 right:20px;
103 width:260px;
104 background:#111;
105 border-radius:10px;
106 overflow:hidden;
107 }
108
109 #chat-header{
110 background:#8c52ff;
111 padding:10px;
112 text-align:center;
113 }
114
115 #chat-body{
116 height:180px;
117 overflow:auto;
118 padding:10px;
119 font-size:14px;
120 }
121
122 #chat-input{
123 width:100%;
124 padding:10px;
125 border:none;
126 background:#000;
127 color:white;
128 }
129
130 </style>
131
132 </head>
133
134 <body>
135
136 <section class="hero">
137
138 <h1>Rani Patel</h1>
139
140 <div class="typing">
141 <span id="typing"></span>
142 </div>
143
144 <img src="https://capsule-render.vercel.app/api?type=waving&color=0:8c52ff,100:00d2ff&height=150&section=header&text=Creative%20Developer">
145
146 </section>
147
148 <section>
149
150 <h2>3D Tech Stack</h2>
151
152 <div class="tech-sphere">
153
154 <div class="tech-item"><i class="fab fa-html5"></i></div>
155 <div class="tech-item"><i class="fab fa-css3-alt"></i></div>
156 <div class="tech-item"><i class="fab fa-js"></i></div>
157 <div class="tech-item"><i class="fab fa-react"></i></div>
158 <div class="tech-item"><i class="fab fa-node-js"></i></div>
159 <div class="tech-item"><i class="fab fa-git-alt"></i></div>
160 <div class="tech-item"><i class="fab fa-github"></i></div>
161
162 </div>
163
164 </section>
165
166 <section>
167
168 <h2>Projects</h2>
169
170 <div class="projects">
171
172 <div class="project-card">BigBasket Clone</div>
173 <div class="project-card">Porter Clone</div>
174 <div class="project-card">BBC News Clone</div>
175 <div class="project-card">AI Chatbot</div>
176
177 </div>
178
179 </section>
180
181 <section class="github">
182
183 <h2>GitHub Stats</h2>
184
185 <img src="https://github-readme-stats.vercel.app/api?username=RaniPatel16&show_icons=true&theme=tokyonight">
186
187 <img src="https://github-readme-streak-stats.herokuapp.com/?user=RaniPatel16&theme=tokyonight">
188
189 <img src="https://github-profile-trophy.vercel.app/?username=RaniPatel16&theme=tokyonight">
190
191 <img src="https://github-readme-activity-graph.vercel.app/graph?username=RaniPatel16&theme=tokyo-night">
192
193 <img src="https://raw.githubusercontent.com/Platane/snk/output/github-contribution-grid-snake.svg">
194
195 </section>
196
197 <section>
198
199 <h2>Contact</h2>
200
201 <p>LinkedIn</p>
202 <p>GitHub</p>
203 <p>Phone: 9898225910</p>
204
205 </section>
206
207 <div id="chatbot">
208
209 <div id="chat-header">AI Assistant</div>
210
211 <div id="chat-body"></div>
212
213 <input id="chat-input" placeholder="Ask about Rani">
214
215 </div>
216
217 <script>
218
219 const words=["Frontend Developer","UI Designer","React Developer","Creative Coder"];
220
221 let i=0;
222 let j=0;
223 let deleting=false;
224
225 function type(){
226
227 let word=words[i];
228
229 document.getElementById("typing").innerText=
230 deleting?word.substring(0,j--):word.substring(0,j++);
231
232 if(!deleting && j===word.length){
233 deleting=true;
234 setTimeout(type,1000);
235 return;
236 }
237
238 if(deleting && j===0){
239 deleting=false;
240 i=(i+1)%words.length;
241 }
242
243 setTimeout(type,deleting?40:80);
244
245 }
246
247 type();
248
249 </script>
250
251 </body>
252 </html>

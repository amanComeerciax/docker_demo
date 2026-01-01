

<h1>🐳 Docker Basics – Node.js Practice Project</h1>

<p>
This repository documents my hands-on practice with <b>Docker</b> using a simple
<b>Node.js + Express</b> application.  
The goal was to understand how Docker images and containers work in real projects.
</p>

---

<h2>🚀 What I Learned</h2>
<ul>
  <li>What Docker is and why it is used</li>
  <li>Difference between <b>Image</b> and <b>Container</b></li>
  <li>How to Dockerize a Node.js project</li>
  <li>How to build, run, stop, and remove containers</li>
  <li>How ports work inside Docker</li>
</ul>

---

<h2>📦 Project Overview</h2>

<div class="box">
<b>Tech Stack:</b><br/>
• Node.js<br/>
• Express.js<br/>
• Docker<br/>
</div>

<p>
This is a small Express server that runs inside a Docker container.
</p>

---

<h2>📁 Project Structure</h2>

<pre>
project/
│── Dockerfile
│── package.json
│── index.js
│── .dockerignore
│── README.html
</pre>

---

<h2>📄 index.js (Simple Node App)</h2>

<pre><code>
const express = require("express");
const app = express();

app.get("/", (req, res) => {
  res.send("Docker is working 🚀");
});

app.listen(3000, () => {
  console.log("Server running on port 3000");
});
</code></pre>

---

<h2>🐳 Dockerfile</h2>

<pre><code>
FROM node:18

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 3000

CMD ["node", "index.js"]
</code></pre>

---

<h2>🚫 .dockerignore</h2>

<pre><code>
node_modules
.git
.env
</code></pre>

---

<h2>⚙️ Docker Commands Used</h2>

<h3>🔍 Check Docker Version</h3>
<pre><code>docker --version</code></pre>

<h3>📃 List Running Containers</h3>
<pre><code>docker ps</code></pre>

<h3>📃 List All Containers</h3>
<pre><code>docker ps -a</code></pre>

<h3>📦 Build Docker Image</h3>
<pre><code>docker build -t my-node-app .</code></pre>

<h3>▶️ Run Container</h3>
<pre><code>docker run -p 3000:3000 my-node-app</code></pre>

<h3>▶️ Run in Background (Detached Mode)</h3>
<pre><code>docker run -d -p 3000:3000 my-node-app</code></pre>

<h3>⏹ Stop Container</h3>
<pre><code>docker stop &lt;container_id&gt;</code></pre>

<h3>🗑 Remove Container</h3>
<pre><code>docker rm &lt;container_id&gt;</code></pre>

<h3>🗑 Remove Image</h3>
<pre><code>docker rmi my-node-app</code></pre>

---

<h2>🧠 Core Docker Concepts (Simple)</h2>

<div class="box">
<b>Docker Image:</b><br/>
Blueprint of the app (code + dependencies)
</div>

<div class="box">
<b>Docker Container:</b><br/>
Running instance of an image
</div>

<div class="box">
<b>Port Mapping:</b><br/>
<code>-p 3000:3000</code> → Local port 3000 mapped to container port 3000
</div>

---

<h2>🌐 How to Access the App</h2>

<p>
After running the container:
</p>

<pre><code>
http://localhost:3000
</code></pre>

---

<h2>✅ Outcome</h2>
<ul>
  <li>Successfully Dockerized a Node.js app</li>
  <li>Understood real-world Docker workflow</li>
  <li>Ready to Dockerize MERN projects</li>
</ul>

---

<h2>📌 Next Steps</h2>
<ul>
  <li>Docker Compose</li>
  <li>MERN stack Dockerization</li>
  <li>Production-ready Docker setup</li>
</ul>

---

<p><b>Author:</b> Aman Memon</p>
<p><b>Purpose:</b> Docker learning & practice</p>

</body>
</html>

# Pixora
index.html
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <title>Pixora</title>
  <link rel="stylesheet" href="style.css">
</head>
<body class="dark">

<header>
  <h1>✨ Pixora</h1>
  <a href="login.html" class="btn">Entrar</a>
</header>

<section class="hero">
  <h2>Crie designs incríveis com IA</h2>
  <p>Editor profissional estilo Canva</p>
  <a href="editor.html" class="btn-primary">Começar Agora</a>
</section>

<section class="features">
  <div>🎨 Templates prontos</div>
  <div>🤖 IA criativa</div>
  <div>💰 Monetize seus designs</div>
</section>

</body>
</html>
<!DOCTYPE html>
<html>
<head>
  <title>Login - Pixora</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

<div class="login-box">
  <h2>Entrar no Pixora</h2>
  <input type="email" placeholder="Email">
  <input type="password" placeholder="Senha">
  <button onclick="login()">Entrar</button>
</div>

<script>
function login(){
  alert("Login simulado 🚀");
  window.location.href = "editor.html";
}
</script>

</body>
</html>
<!DOCTYPE html>
<html>
<head>
  <title>Editor - Pixora</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

<div class="sidebar">
  <button onclick="addText()">Texto</button>
  <button onclick="addShape()">Forma</button>
  <button onclick="loadTemplate()">Template</button>
  <button onclick="generateAI()">IA ✨</button>
</div>

<div class="canvas" id="canvas"></div>

<script src="editor.js"></script>
<script src="templates.js"></script>

</body>
</html>
body.dark {
  background: #0f172a;
  color: white;
  font-family: Arial;
}

header {
  display: flex;
  justify-content: space-between;
  padding: 20px;
}

.hero {
  text-align: center;
  margin-top: 80px;
}

.btn, .btn-primary {
  padding: 10px 20px;
  background: #6366f1;
  color: white;
  border: none;
  text-decoration: none;
}

.features {
  display: flex;
  justify-content: space-around;
  margin-top: 50px;
}

.sidebar {
  position: fixed;
  width: 150px;
  height: 100%;
  background: #1e293b;
  padding: 10px;
}

.canvas {
  margin-left: 170px;
  height: 100vh;
  background: white;
  position: relative;
}
const canvas = document.getElementById("canvas");

function addText(){
  const el = document.createElement("div");
  el.innerText = "Texto";
  el.contentEditable = true;
  styleElement(el);
  canvas.appendChild(el);
}

function addShape(){
  const el = document.createElement("div");
  el.style.width = "100px";
  el.style.height = "100px";
  el.style.background = "blue";
  styleElement(el);
  canvas.appendChild(el);
}

function styleElement(el){
  el.style.position = "absolute";
  el.style.top = "50px";
  el.style.left = "50px";
  el.draggable = true;

  el.ondragend = (e)=>{
    el.style.left = e.pageX + "px";
    el.style.top = e.pageY + "px";
  }
}

function generateAI(){
  const prompt = prompt("Descreva a imagem:");
  alert("IA vai gerar: " + prompt);
}function loadTemplate(){
  const canvas = document.getElementById("canvas");

  canvas.innerHTML = `
    <div style="position:absolute; top:50px; left:50px; font-size:30px;">
      Promoção 50% OFF
    </div>
    <div style="position:absolute; top:120px; left:50px;">
      Só hoje!
    </div>
  `;
}

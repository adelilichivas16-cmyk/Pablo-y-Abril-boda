 <!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Invitación de Boda - Abril & Pablo</title>
<link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Playfair+Display:wght@400;700&display=swap" rel="stylesheet">
<style>
/* --- ESTILOS GENERALES --- */
body{
    margin:0;
    font-family:'Playfair Display',serif;
    background: radial-gradient(circle at top,#e0f0ff,#b5c6e0,#8da0c9);
    color:#2b2b2b;
    text-align:center;
    overflow-x:hidden;
}
h1,h2,h3{
    font-family:'Great Vibes',cursive;
    color:#395886;
}

/* --- OVERLAY INICIAL --- */
.overlay{
    position:fixed;
    top:0; left:0;
    width:100%; height:100%;
    background: radial-gradient(circle at center,rgba(255,255,255,0.95),rgba(200,200,255,0.85));
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
    z-index:10;
    transition:opacity 1.5s ease;
}
.overlay h1{
    font-size:3em;
    margin-bottom:20px;
}
.ring{
    width:130px;
    height:130px;
    background-image:url('ring.png');
    background-size:contain;
    background-repeat:no-repeat;
    cursor:pointer;
    animation:glow 2s infinite alternate,rotate 6s linear infinite;
}
@keyframes glow{
    from{filter:drop-shadow(0 0 5px #c0c0ff);}
    to{filter:drop-shadow(0 0 15px #80a0ff);}
}
@keyframes rotate{
    0%{transform:rotate(0deg);}
    100%{transform:rotate(360deg);}
}

/* --- INVITACION --- */
.invitation{
    opacity:0;
    transform:scale(0.5);
    transition:all 1.8s ease;
    position:relative;
    z-index:5;
}
.invitation.active{
    opacity:1;
    transform:scale(1);
}
h2{font-size:2.5em; margin-bottom:20px;}
.section{
    background:rgba(255,255,255,0.85);
    margin:40px auto;
    padding:25px 20px;
    border-radius:25px;
    max-width:750px;
    box-shadow:0 0 25px rgba(180,200,255,0.5);
    position:relative;
    overflow:hidden;
    transform:scale(0.95);
    opacity:0;
    transition:all 1.5s ease;
}
.section.visible{
    transform:scale(1);
    opacity:1;
}
.mapa iframe{
    width:100%;
    height:300px;
    border-radius:15px;
    border:none;
}
#countdown{
    font-size:1.6em;
    color:#395886;
    font-weight:bold;
}
footer{
    margin-top:20px;
    padding:20px;
}
.whatsapp{
    display:inline-block;
    margin:10px;
    background:#25D366;
    color:white;
    padding:12px 22px;
    border-radius:50px;
    text-decoration:none;
    font-weight:bold;
}

/* --- COMENTARIOS --- */
.comments textarea{
    width:90%;
    border-radius:12px;
    border:1px solid #ccc;
    padding:8px;
}
.comments button{
    margin-top:10px;
    padding:10px 20px;
    border:none;
    border-radius:25px;
    background:#395886;
    color:white;
    font-weight:bold;
    cursor:pointer;
}

/* --- LUCES Y FLORES --- */
.luces,.flores{
    position:fixed;
    top:0; left:0;
    width:100%; height:100%;
    pointer-events:none;
    overflow:hidden;
    z-index:1;
}
.luz,.flor{
    position:absolute;
    border-radius:50%;
    opacity:0.8;
}
.luz{
    width:6px;
    height:6px;
    background:white;
    animation:flotar 6s infinite ease-in-out;
}
.flor{
    width:14px;
    height:14px;
    background:rgba(255,255,255,0.7);
    box-shadow:0 0 10px rgba(255,255,255,0.6);
    animation:flotar 12s linear infinite;
}
@keyframes flotar{
    0%{transform:translateY(0) scale(1);opacity:1;}
    100%{transform:translateY(-120vh) scale(0.5);opacity:0;}
}

/* --- SECCION FOTOS --- */
.moments img{
    width:32%;
    margin:1%;
    border-radius:15px;
    box-shadow:0 0 15px rgba(100,120,180,0.4);
    transition:transform 0.5s ease;
}
.moments img:hover{
    transform:scale(1.05);
}
.moments p{
    font-size:1.2em;
    margin-top:15px;
    font-style:italic;
    color:#395886;
}
</style>
</head>
<body>

<div class="overlay" id="overlay">
    <h1>Con amor eterno,<br>Abril & Pablo</h1>
    <div class="ring" id="ring"></div>
</div>

<audio id="music" loop>
    <source src="eternamente-enamorados.mp3" type="audio/mpeg">
</audio>

<div class="invitation" id="invitation">
    <h2>Nos complace invitarte a nuestra boda</h2>

    <!-- DATOS DE LOS NOVIOS -->
    <div class="section">
        <p><strong>Abril Pérez Aguilar</strong><br>Hija de Eva Aguilar Rendón y Pedro Pérez Hernández</p>
        <p><strong>Pablo Eliel Tinoco Hernández</strong><br>Hijo de Saray Hernández Santana y Pablo Tinoco Carranza (finado)</p>
    </div>

    <!-- CEREMONIA Y RECEPCION -->
    <div class="section">
        <h3>Ceremonia Religiosa</h3>
        <p>2:00 p.m. - Jardín El Abuelo, Tlaquiltenango</p>
        <h3>Recepción</h3>
        <p>4:00 p.m. - Jardín El Abuelo, Tlaquiltenango</p>
        <p><em>"Y los dos serán una sola carne" - Mateo 19:6</em></p>
    </div>

    <!-- MAPA -->
    <div class="section mapa">
        <h3>Ubicación</h3>
        <iframe src="https://www.bing.com/maps?&ty=18&q=Jard%C3%ADn%20El%20Abuelo%2C%20Tlaquiltenango%2C%20Morelos%2C%20M%C3%A9xico&ss=ypid.YN9001x10312454619790021630&mb=18.631809~-99.165076~18.622903~-99.151279&description=Tlaquiltenango%2C%2062980%20Morelos%2C%20Morelos%C2%B7Estadios%20y%20recintos%20para%20eventos&cardbg=%23219AB6&dt=1759586400000&tt=Jard%C3%ADn%20El%20Abuelo&tsts1=%2526ty%253D18%2526q%253DJard%2525C3%2525ADn%252520El%252520Abuelo%25252C%252520Tlaquiltenango%25252C%252520Morelos%25252C%252520M%2525C3%2525A9xico%2526ss%253Dypid.YN9001x10312454619790021630%2526mb%253D18.631809~-99.165076~18.622903~-99.151279%2526description%253DTlaquiltenango%25252C%25252062980%252520Morelos%25252C%252520Morelos%2525C2%2525B7Estadios%252520y%252520recintos%252520para%252520eventos%2526cardbg%253D%252523219AB6%2526dt%253D1759586400000&tstt1=Jard%C3%ADn%20El%20Abuelo&cp=18.627356~-99.163499&lvl=16&pi=0&ftst=1&ftics=True&v=2&sV=2&form=S00027" allowfullscreen></iframe>
    </div>

    <!-- CONTADOR -->
    <div class="section">
        <h3>Faltan...</h3>
        <div id="countdown"></div>
    </div>

    <!-- NUESTROS MOMENTOS -->
    <div class="section moments">
        <h3>Nuestros hermosos momentos</h3>
        <div>
            <img src="images/foto1.jpg" alt="Momento 1">
            <img src="images/foto2.jpg" alt="Momento 2">
            <img src="images/foto3.jpg" alt="Momento 3">
        </div>
        <p>Tu amor es lo que he anhelado y el regalo que Dios me ha dado</p>
    </div>

    <!-- COMENTARIOS -->
    <div class="section comments">
        <h3>Deja tus buenos deseos 💌</h3>
        <form>
            <textarea rows="4" placeholder="Escribe aquí tu mensaje..."></textarea><br>
            <button type="button">Enviar</button>
        </form>
    </div>

    <!-- WHATSAPP -->
    <footer class="section">
        <a href="https://wa.me/5217774914500" class="whatsapp">WhatsApp Abril 💐</a>
        <a href="https://wa.me/5217341123645" class="whatsapp">WhatsApp Pablo 🤵</a>
    </footer>
</div>

<div class="luces" id="luces"></div>
<div class="flores" id="flores"></div>

<script>
// ELEMENTOS
const overlay=document.getElementById('overlay');
const ring=document.getElementById('ring');
const invitation=document.getElementById('invitation');
const music=document.getElementById('music');
const lucesContainer=document.getElementById('luces');
const floresContainer=document.getElementById('flores');

// LUCES
for(let i=0;i<25;i++){
    const luz=document.createElement('div');
    luz.classList.add('luz');
    luz.style.left=Math.random()*100+'vw';
    luz.style.animationDuration=(4+Math.random()*4)+'s';
    luz.style.animationDelay=Math.random()*3+'s';
    lucesContainer.appendChild(luz);
}

// FLORES
for(let i=0;i<15;i++){
    const flor=document.createElement('div');
    flor.classList.add('flor');
    flor.style.left=Math.random()*100+'vw';
    flor.style.animationDuration=(10+Math.random()*10)+'s';
    flor.style.animationDelay=Math.random()*5+'s';
    floresContainer.appendChild(flor);
}

// ABRIR INVITACION
ring.addEventListener('click',()=>{
    overlay.style.opacity='0';
    setTimeout(()=>{
        overlay.style.display='none';
        invitation.classList.add('active');
        music.play();
        checkVisibility();
    },1500);
});

// CONTADOR
const eventDate=new Date("December 28, 2025 14:00:00").getTime();
const countdown=document.getElementById('countdown');
setInterval(()=>{
    const now=new Date().getTime();
    const distance=eventDate-now;
    const days=Math.floor(distance/(1000*60*60*24));
    const hours=Math.floor((distance%(1000*60*60*24))/(1000*60*60));
    const minutes=Math.floor((distance%(1000*60*60))/(1000*60));
    countdown.innerHTML=`${days} días, ${hours} horas, ${minutes} minutos`;
},1000);

// ZOOM SECCIONES AL SCROLL
const sections=document.querySelectorAll('.section');
function checkVisibility(){
    const triggerBottom=window.innerHeight/5*4;
    sections.forEach(section=>{
        const sectionTop=section.getBoundingClientRect().top;
        if(sectionTop<triggerBottom){section.classList.add('visible');}
    });
}
window.addEventListener('scroll',checkVisibility);
</script>

</body>
</html>
[eternamente.mp3](https://github.com/user-attachments/files/22700948/eternamente.mp3)
![photo3 - copia](https://github.com/user-attachments/assets/f9ab1dba-cbe1-457d-b9d3-9cce0b50892b)
![photo2 - copia](https://github.com/user-attachments/assets/d6f58b76-8124-4f8b-b68e-1a53a90d67d4)
![photo1 - copia](https://github.com/user-attachments/assets/ea07e08f-5314-4660-a158-aa4e7ee273da)
![momentos3 - copia](https://github.com/user-attachments/assets/3aa539ff-21e5-4f8d-8c1b-ffa149c22586)
![momentos2 - copia](https://github.com/user-attachments/assets/febb7121-1ecd-4a74-b48f-35c225ae7bb0)
![momento1 - copia](https://github.com/user-attachments/assets/ab2f1322-2e0d-42dd-8383-920de17385f9)
![ring - copia](https://github.com/user-attachments/assets/7e02ddff-078b-45e7-b7df-6e8ab704f3fd)

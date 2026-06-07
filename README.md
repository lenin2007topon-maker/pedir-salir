html
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>¿Quieres salir conmigo?</title>

<style>
body{
    margin:0;
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    background:linear-gradient(135deg,#ffd6e7,#ffffff);
    font-family:'Arial',sans-serif;
    overflow:hidden;
}

.container{
    text-align:center;
    background:rgba(255,255,255,0.9);
    padding:40px;
    border-radius:25px;
    box-shadow:0 0 25px rgba(255,105,180,0.3);
}

h1{
    color:#ff4d94;
    font-size:2.5rem;
}

p{
    color:#666;
    font-size:1.2rem;
}

.buttons{
    margin-top:30px;
}

button{
    padding:15px 30px;
    font-size:1.2rem;
    border:none;
    border-radius:50px;
    cursor:pointer;
    transition:0.3s;
}

#si{
    background:#ff69b4;
    color:white;
    margin-right:20px;
}

#si:hover{
    transform:scale(1.1);
}

#no{
    background:white;
    color:#ff69b4;
    border:2px solid #ff69b4;
    position:absolute;
}

#mensaje{
    display:none;
    margin-top:20px;
    font-size:1.5rem;
    color:#ff1493;
    animation:aparecer 1s ease;
}

@keyframes aparecer{
    from{opacity:0; transform:scale(0.5);}
    to{opacity:1; transform:scale(1);}
}

.corazon{
    position:absolute;
    color:#ff69b4;
    font-size:20px;
    animation:flotar 5s linear infinite;
}

@keyframes flotar{
    from{
        transform:translateY(100vh);
        opacity:1;
    }
    to{
        transform:translateY(-100px);
        opacity:0;
    }
}
</style>
</head>
<body>

<div class="container">
    <h1>💖 ¿Quieres salir conmigo? 💖</h1>
    <p>Eres la persona más especial del mundo para mí 🥰</p>

    <div class="buttons">
        <button id="si">Sí ❤️</button>
        <button id="no">No 😜</button>
    </div>

    <div id="mensaje">
        ✨ ¡Sabía que dirías que sí! ✨<br>
        ❤️ Te prometo una cita increíble ❤️
    </div>
</div>

<script>
const btnNo = document.getElementById("no");

btnNo.addEventListener("mouseover", () => {
    const x = Math.random() * (window.innerWidth - 120);
    const y = Math.random() * (window.innerHeight - 60);

    btnNo.style.left = x + "px";
    btnNo.style.top = y + "px";
});

document.getElementById("si").addEventListener("click", () => {
    document.getElementById("mensaje").style.display = "block";
});

function crearCorazon(){
    const corazon = document.createElement("div");
    corazon.classList.add("corazon");
    corazon.innerHTML = "💖";
    corazon.style.left = Math.random() * window.innerWidth + "px";
    corazon.style.fontSize = (Math.random() * 20 + 15) + "px";

    document.body.appendChild(corazon);

    setTimeout(() => {
        corazon.remove();
    }, 5000);
}

setInterval(crearCorazon, 400);
</script>

</body>
</html>

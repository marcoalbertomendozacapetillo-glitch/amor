<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Carta para ti ❤️</title>

<style>
body{
    background:#ffdde1;
    display:flex;
    justify-content:center;
    align-items:center;
    height:100vh;
    font-family:Arial;
}

.carta{
    width:300px;
    height:200px;
    background:white;
    position:relative;
    border-radius:10px;
    box-shadow:0 10px 20px rgba(0,0,0,0.2);
    cursor:pointer;
    overflow:hidden;
}

.tapa{
    position:absolute;
    width:100%;
    height:100%;
    background:#ff6b81;
    clip-path:polygon(0 0,100% 0,50% 60%);
    transition:1s;
}

.carta.abierta .tapa{
    transform:rotateX(180deg);
    transform-origin:top;
}

.corazon{
    position:absolute;
    top:70px;
    left:130px;
    font-size:40px;
    animation:latir 1s infinite;
}

@keyframes latir{
    0%{transform:scale(1);}
    50%{transform:scale(1.2);}
    100%{transform:scale(1);}
}

.mensaje{
    position:absolute;
    top:90px;
    width:100%;
    text-align:center;
    padding:10px;
    opacity:0;
    transition:1s;
}

.carta.abierta .mensaje{
    opacity:1;
}
</style>
</head>

<body>

<div class="carta" onclick="abrirCarta()" id="carta">
<div class="tapa"></div>
<div class="corazon">❤️</div>
<div class="mensaje" id="texto"></div>
</div>

<script>
function abrirCarta(){
document.getElementById("carta").classList.toggle("abierta");
}

const params = new URLSearchParams(window.location.search);
const mensaje = params.get("msg") || "se que no me conoces tambien y yo tampoco pero me gustaria que me des la oportunidad de demostrarte cuanto me gustas de vedad por esto hago esta carta eres especial para mi amoroso carilloso y sobre todo hay interes  ❤️";

document.getElementById("texto").innerText = mensaje;
</script>

</body>
</html>

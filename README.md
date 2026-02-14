# tanmay-be-my-valentine
Frontend project with inevitable outcomes.
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>TANMAY NEGI 💖</title>

<link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@600&family=Poppins:wght@300;500&display=swap" rel="stylesheet">

<style>
* { margin:0; padding:0; box-sizing:border-box; font-family:'Poppins', sans-serif; }

body {
    height:100vh;
    overflow:hidden;
    background:
    linear-gradient(to top, rgba(255,182,193,0.5), rgba(255,228,225,0.6)),
    url('https://images.unsplash.com/photo-1501785888041-af3ef285b470') no-repeat center center/cover;
    display:flex;
    justify-content:center;
    align-items:center;
    text-align:center;
    color:#4a2c2a;
}

.container {
    background:rgba(255,255,255,0.88);
    padding:40px;
    border-radius:20px;
    backdrop-filter:blur(8px);
    box-shadow:0 10px 40px rgba(0,0,0,0.2);
    max-width:520px;
    width:90%;
}

h1 {
    font-family:'Dancing Script', cursive;
    font-size:38px;
    margin-bottom:10px;
}

h2 {
    font-size:22px;
    margin-bottom:20px;
}

#beagle {
    width:220px;
    border-radius:15px;
    margin-bottom:25px;
    transition:0.4s ease;
}

.buttons {
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:15px;
}

button {
    padding:12px;
    border-radius:25px;
    border:none;
    background:#ff6f91;
    color:white;
    font-weight:500;
    cursor:pointer;
    transition:0.3s ease;
}

button:hover {
    transform:scale(1.05);
    background:#ff4e78;
}

#celebration {
    display:none;
    margin-top:20px;
    font-size:20px;
    font-weight:bold;
}

/* Floating Puppies */
.puppy {
    position:absolute;
    width:90px;
    animation:float 6s ease-in-out infinite;
    opacity:0.9;
}

.puppy.left { bottom:15px; left:15px; }
.puppy.right { bottom:15px; right:15px; }

@keyframes float {
    0%{ transform:translateY(0); }
    50%{ transform:translateY(-15px); }
    100%{ transform:translateY(0); }
}

/* Confetti */
.confetti {
    position:absolute;
    width:10px;
    height:10px;
    top:-10px;
    animation:fall 3s linear infinite;
}

@keyframes fall {
    to { transform:translateY(100vh) rotate(360deg); }
}

.music-btn {
    margin-top:15px;
    font-size:14px;
    background:transparent;
    color:#ff4e78;
    border:1px solid #ff4e78;
}
</style>
</head>

<body>

<!-- POST MALONE -->
<iframe id="postSong" style="border-radius:12px; position:absolute; top:-200px;"
src="https://open.spotify.com/embed/track/21jGcNKet2qwijlDFuPiPb"
width="300" height="80"
allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture">
</iframe>

<!-- DAFT PUNK -->
<iframe id="daftSong" style="border-radius:12px; position:absolute; top:-200px; display:none;"
src="https://open.spotify.com/embed/track/0DiWol3AO6WpXZgp0goxAV"
width="300" height="80"
allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture">
</iframe>

<img src="https://pngimg.com/uploads/dog/dog_PNG50339.png" class="puppy left">
<img src="https://pngimg.com/uploads/dog/dog_PNG50339.png" class="puppy right">

<div class="container">
    <h1>TANMAY NEGI</h1>
    <h2>Will you be my Valentine?</h2>

    <img id="beagle" src="https://media.giphy.com/media/3oriO0OEd9QIDdllqo/giphy.gif">

    <div class="buttons">
        <button onclick="celebrate()">💖 Yes</button>
        <button onclick="celebrate()">💕 Of course</button>
        <button onclick="celebrate()">🥺 I’m dying to be</button>
        <button onclick="celebrate()">💘 I was born to be one</button>
    </div>

    <button class="music-btn" onclick="enableMusic()">🔊 Tap for Vibes</button>

    <div id="celebration">
        You were always meant to choose this. 💘
    </div>
</div>

<script>
function enableMusic(){
    document.getElementById("postSong").style.top = "10px";
}

function celebrate(){
    document.getElementById("beagle").src =
    "https://media.giphy.com/media/l0MYt5jPR6QX5pnqM/giphy.gif";

    document.getElementById("celebration").style.display="block";

    document.getElementById("postSong").style.display="none";
    document.getElementById("daftSong").style.display="block";
    document.getElementById("daftSong").style.top="10px";

    launchConfetti();
}

function launchConfetti(){
    for(let i=0;i<40;i++){
        let confetti=document.createElement("div");
        confetti.classList.add("confetti");
        confetti.style.left=Math.random()*window.innerWidth+"px";
        confetti.style.backgroundColor=`hsl(${Math.random()*360},100%,70%)`;
        confetti.style.animationDuration=(Math.random()*2+2)+"s";
        document.body.appendChild(confetti);
        setTimeout(()=>confetti.remove(),3000);
    }
}
</script>

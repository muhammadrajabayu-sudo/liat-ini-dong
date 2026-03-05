<!DOCTYPE html>
<html>
<head>
<title>Pesan Rahasia</title>

<style>

body{
background: linear-gradient(135deg,#ff758c,#ff7eb3);
font-family: Arial;
text-align:center;
height:100vh;
overflow:hidden;
color:white;
}

h1{
margin-top:80px;
}

button{
padding:12px 25px;
font-size:18px;
border:none;
border-radius:10px;
cursor:pointer;
margin:10px;
}

#iya{
background:white;
}

#tidak{
background:white;
position:absolute;
}

#pesan{
font-size:22px;
margin-top:30px;
}

/* animasi hati */

.heart{
position:fixed;
top:-10px;
color:red;
animation:jatuh 5s linear infinite;
}

@keyframes jatuh{
0%{transform:translateY(-10px);}
100%{transform:translateY(100vh);}
}

</style>
</head>

<body>

<h1>Hai Kamu 😊</h1>

<p id="pesan">Klik tombol di bawah ini dulu...</p>

<button onclick="mulai()">Mulai</button>

<div id="pertanyaan" style="display:none;">
<h2>Maukah kamu jadi orang spesialku? ❤️</h2>

<button id="iya" onclick="jawab()">Mau</button>
<button id="tidak" onmouseover="lari()">Tidak</button>
</div>

<script>

let kata = [
"Kamu tau ga? Dunia ini luas...",
"Tapi anehnya pikiranku selalu kembali ke kamu.",
"Aku mencoba fokus ke banyak hal...",
"Tapi yang paling sering muncul tetap wajah kamu.",
"Dan akhirnya aku sadar sesuatu..."
];

let i = 0;

function mulai(){

if(i < kata.length){
document.getElementById("pesan").innerHTML = kata[i];
i++;
}
else{
document.getElementById("pesan").style.display="none";
document.querySelector("button").style.display="none";
document.getElementById("pertanyaan").style.display="block";
}

}

function jawab(){
alert("Yeay! Sekarang kamu resmi jadi orang paling spesial di hidupku ❤️");
}

function lari(){
let x = Math.random()*window.innerWidth;
let y = Math.random()*window.innerHeight;

let btn = document.getElementById("tidak");

btn.style.left = x + "px";
btn.style.top = y + "px";
}

/* membuat hati jatuh */

setInterval(function(){

let heart = document.createElement("div");
heart.innerHTML="❤️";
heart.className="heart";

heart.style.left=Math.random()*100+"vw";
heart.style.fontSize=(Math.random()*20+10)+"px";

document.body.appendChild(heart);

setTimeout(()=>{heart.remove()},5000);

},300);

</script>

</body>
</html>

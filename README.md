<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy Friendship Day ❤️</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">

<script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>

<style>

*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:'Poppins',sans-serif;
}

body{

background:linear-gradient(135deg,#6a11cb,#2575fc);
display:flex;
justify-content:center;
align-items:center;
min-height:100vh;
overflow:hidden;
padding:20px;

}

/* Floating Hearts */

body::before{
content:"💙";
position:absolute;
font-size:40px;
left:5%;
animation:float 7s linear infinite;
}

body::after{
content:"🤝";
position:absolute;
font-size:45px;
right:5%;
animation:float2 8s linear infinite;
}

@keyframes float{

0%{transform:translateY(100vh) rotate(0deg);}
100%{transform:translateY(-120vh) rotate(360deg);}
}

@keyframes float2{

0%{transform:translateY(120vh);}
100%{transform:translateY(-120vh);}
}

.card{

width:100%;
max-width:700px;
background:rgba(255,255,255,.15);
backdrop-filter:blur(15px);
border-radius:25px;
padding:40px;
text-align:center;
box-shadow:0 15px 40px rgba(0,0,0,.25);
color:white;
animation:fadeIn 1s ease;

}

@keyframes fadeIn{

from{
opacity:0;
transform:translateY(30px);
}
to{
opacity:1;
transform:translateY(0);
}

}

h1{

margin-bottom:20px;

}

input{

width:100%;
padding:15px;
font-size:18px;
border:none;
border-radius:50px;
outline:none;
margin:20px 0;
text-align:center;

}

button{

padding:15px 40px;
font-size:18px;
border:none;
border-radius:50px;
background:#ff4b8b;
color:white;
cursor:pointer;
transition:.3s;
font-weight:bold;

}

button:hover{

transform:scale(1.05);
background:#ff1d6f;

}

.hidden{
display:none;
}

.friend-name{

font-size:35px;
font-weight:bold;
color:#ffe600;
margin-bottom:20px;

}

.msg{

line-height:2;
font-size:18px;
margin-top:20px;

}

.congrats{

font-size:28px;
font-weight:bold;
color:#00ff9d;
margin-bottom:20px;

}

.footer{

margin-top:30px;
font-size:22px;
font-weight:bold;

}

@media(max-width:600px){

.card{
padding:25px;
}

.friend-name{
font-size:28px;
}

.msg{
font-size:16px;
}

}

</style>
</head>

<body>

<div class="card">

<div id="loginPage">

<h1>🤝 Happy Friendship Day 💙</h1>

<p>Enter your beautiful name ❤️</p>

<input
type="text"
id="name"
placeholder="Your Name">

<button onclick="login()">Login</button>

</div>

<div id="wishPage" class="hidden">

<div class="congrats">
🎉 Congratulations! 🎉
</div>

<h2>You're added to my <br>
❤️ Best Friend List ❤️
</h2>

<br>

<div class="friend-name" id="friendName"></div>

<div class="msg">

Happy Friendship Day! 🤝💙

<br><br>

A true friend is someone who stands by you through every high and low, makes life brighter with laughter, and turns ordinary moments into unforgettable memories.

<br><br>

Thank you for being a part of my journey.

Wishing you endless happiness, success, good health, and countless beautiful memories.

May our friendship continue to grow stronger with every passing year.

<br><br>

Have an amazing Friendship Day! 🌸✨

</div>

<div class="footer">

❤️ Forever Friends ❤️

</div>

</div>

</div>

<script>

function login(){

let name=document.getElementById("name").value.trim();

if(name===""){
alert("Please enter your name ❤️");
return;
}

document.getElementById("loginPage").classList.add("hidden");
document.getElementById("wishPage").classList.remove("hidden");

document.getElementById("friendName").innerHTML="Dear "+name+" 💙";

confetti({

particleCount:250,
spread:180,
origin:{y:0.6}

});

}

</script>

</body>
</html>

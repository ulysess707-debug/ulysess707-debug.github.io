# ulysess707-debug.github.io

<!DOCTYPE html>
<html>
<head>
<title>Our One Month ❤️</title>

<style>
body{
margin:0;
font-family:Arial;
background:linear-gradient(135deg,#ff758c,#ff7eb3);
color:white;
text-align:center;
overflow-x:hidden;
}

#lock{
position:fixed;
top:0;
left:0;
width:100%;
height:100%;
background:#ff6b8a;
display:flex;
flex-direction:column;
justify-content:center;
align-items:center;
z-index:10;
}

input{
padding:10px;
border-radius:10px;
border:none;
font-size:16px;
}

button{
background:white;
color:#ff4d6d;
border:none;
padding:12px 25px;
border-radius:12px;
font-size:16px;
cursor:pointer;
margin:10px;
}

.container{
max-width:700px;
margin:auto;
padding:30px;
}

.card{
background:rgba(0,0,0,0.25);
padding:25px;
border-radius:20px;
margin-bottom:25px;
}

.heart{
position:fixed;
bottom:-20px;
font-size:20px;
animation:float 6s linear infinite;
opacity:0.7;
}

@keyframes float{
0%{transform:translateY(0);}
100%{transform:translateY(-100vh);}
}

.hidden{display:none;}
</style>
</head>

<body>

<div id="lock">
<h2>Enter Your Name ❤️</h2>
<input id="nameInput" placeholder="Your name">
<br>
<button onclick="unlock()">Enter</button>
<p id="wrong"></p>
</div>

<div class="container hidden" id="main">

<div class="card">
<h1>Happy One Month ❤️</h1>
<p id="welcome"></p>
</div>

<div class="card">
<h2>Love Letter 💌</h2>
<button onclick="showLetter()">Open Letter</button>

<p id="letter" class="hidden">
Diana,<br><br>

This past month with you has honestly been one of the best times I’ve had in a while.  
I didn’t expect things to feel this easy and this real, but being with you just makes everything better.<br><br>

I like how we can talk, laugh, and just be ourselves without it feeling forced.  
Even the small moments we share end up meaning a lot to me, and I catch myself thinking about them later.<br><br>

You’ve made my days brighter without even trying, and I really appreciate having you in my life.  
Getting to know you has been something I wouldn’t trade for anything.<br><br>

I’m really looking forward to making more memories with you, more laughs, more moments, everything.  
This is just the beginning, and I’m glad it’s with you. ❤️
</p>

</div>

<div class="card">
<h2>Reasons I Love You 💖</h2>
<button onclick="reason()">Generate Reason</button>
<p id="reasonText"></p>
</div>

<div class="card">
<h2>Memory Quiz 🎮</h2>
<p>Who texted first?</p>

<button onclick="quiz('A')">Me</button>
<button onclick="quiz('B')">You</button>

<p id="quizResult"></p>
</div>

</div>

<script>

function unlock(){
let name=document.getElementById("nameInput").value.toLowerCase();

if(name==="diana"){   // password set here

document.getElementById("lock").style.display="none";
document.getElementById("main").classList.remove("hidden");

document.getElementById("welcome").innerHTML="Hey Diana ❤️";

}else{
document.getElementById("wrong").innerHTML="Ahhhh do you know how spell ur first name  ❤️";
}
}

function showLetter(){
document.getElementById("letter").classList.remove("hidden");
}

let reasons=[
"I love the way you make jokes.",
"I love talking to you.",
"I love how you SNOREEE IN UR SLEEP.",
"I love how you make MEEEEEE SPECIAL ED.",
"I love spending time WITTTH YOU DOING MY SEAL NOISES DURR.",
"You just make ME HAPPPERR."
];

function reason(){
let r=Math.floor(Math.random()*reasons.length);
document.getElementById("reasonText").innerHTML=reasons[r];
}

function quiz(ans){
if(ans==="A"){
document.getElementById("quizResult").innerHTML="Correct ❤️";
}else{
document.getElementById("quizResult").innerHTML="Wrong 😭 try again";
}
}

setInterval(()=>{
let heart=document.createElement("div");
heart.className="heart";
heart.innerHTML="❤️";
heart.style.left=Math.random()*100+"vw";
heart.style.fontSize=(15+Math.random()*20)+"px";
heart.style.animationDuration=(4+Math.random()*3)+"s";
document.body.appendChild(heart);

setTimeout(()=>{heart.remove();},6000);
},500);

let msgs=[ q 
"You're special ❤️",
"I appreciate you",
"You make me happy",
"I'm glad I met you",
"You mean a lot to me"
];

setInterval(()=>{
let r=Math.floor(Math.random()*msgs.length);
alert(msgs[r]);
},45000);

</script>

</body>
</html>

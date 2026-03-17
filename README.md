# ulysess707-debug.github.io

<!DOCTYPE html>
<html>
<head>
<title>Our One Month ❤️</title>

<meta name="viewport" content="width=device-width, initial-scale=1.0">

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
padding:12px;
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
bottom:0;
font-size:24px;
animation:float 5s linear infinite;
opacity:1;
z-index:999;
pointer-events:none;
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
Being around you just feels natural, and I really like how easy everything is when we’re together.<br><br>

I catch myself thinking about the little moments we’ve had, and they end up meaning more than I expected.  
You’ve made my days better without even trying, and I appreciate that more than you know.<br><br>

I’m really glad I met you, and I’m excited for everything that’s still ahead for us.  
More memories, more laughs, more time together… all of it. ❤️
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

/* WAIT until page fully loads (important for iPhone) */
document.addEventListener("DOMContentLoaded", function(){

window.unlock = function(){

let name = document.getElementById("nameInput").value.trim().toLowerCase();

if(name === "diana"){

document.getElementById("lock").style.display="none";
document.getElementById("main").classList.remove("hidden");

document.getElementById("welcome").innerHTML="Hey Diana ❤️";

}else{
document.getElementById("wrong").innerHTML="AHHHH DO YOUUU KNOWWW UR FIRSST NAME GURRR ❤️";
}
};

window.showLetter = function(){
document.getElementById("letter").classList.remove("hidden");
};

let reasons=[
"I love how you laughy grrr.",
"I love talking to you with my PWINCESSS.",
"I love your ERRRRMMM ACTUALLY.",
"I love how you make my day better.",
"I love spending time WITTTH UUU.",
"You just make everything VERRRY FUNNY."
];

window.reason = function(){
let r=Math.floor(Math.random()*reasons.length);
document.getElementById("reasonText").innerHTML=reasons[r];
};

window.quiz = function(ans){
if(ans==="A"){
document.getElementById("quizResult").innerHTML="Correct ❤️";
}else{
document.getElementById("quizResult").innerHTML="Wrong 😭 try again";
}
};

/* hearts */
setInterval(()=>{
let heart=document.createElement("div");
heart.className="heart";
heart.innerHTML="💖";
heart.style.left=Math.random()*100+"vw";
heart.style.fontSize=(15+Math.random()*20)+"px";
heart.style.animationDuration=(4+Math.random()*3)+"s";
document.body.appendChild(heart);

setTimeout(()=>{heart.remove();},6000);
},500);

/* messages */
let msgs=[
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

});

</script>

</body>
</html>

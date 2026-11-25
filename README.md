<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Clean Water Awareness</title>
<style>
html {
scroll-behavior: smooth;
}

body {
background-color: powderblue;
font-family: Arial, sans-serif;
margin: 0;
padding-bottom: 80px;
}

.header {
padding: 0;
text-align: center;
background: #1abc9c;
}

.header img {
width: 100%;
max-height: 300px;
object-fit: cover;
display: block;
}

nav {
background-color: #c5e5d8;
padding: 15px;
text-align: center;
}

nav a {
color: #246b57;
margin: 10px;
text-decoration: none;
font-weight: bold;
}

main {
padding: 20px;
}

.age-group {
display: flex;
flex-wrap: wrap;
justify-content: center;
gap: 40px 80px;
max-width: 900px;
margin: 40px auto;
}

.age-box {
background-color: #EAF7FF;
border: 2px solid #87CEFA;
border-radius: 10px;
padding: 25px;
box-sizing: border-box;
width: 320px;
min-height: 220px;
text-align: center;
display: flex;
flex-direction: column;
justify-content: space-between;
align-items: center;
}

.age-box h2 {
color: #006080;
font-size: 23px;
margin-top: 0;
}

.age-box button {
background-color: #c5e5d8;
border: 1px solid #00796B;
border-radius: 5px;
padding: 12px 30px;
font-size: 16px;
cursor: pointer;
margin-bottom: 15px;
}

.age-box button:hover {
background-color: #b0d9c8;
}

.footer {
position: fixed;
left: 0;
bottom: 0;
width: 100%;
background-color: green;
color: white;
text-align: center;
padding: 10px 0;
}

.footer a {
color: white;
margin: 0 10px;
text-decoration: none;
}

.cookie-popup {
position: fixed;
bottom: 60px;
left: 50%;
transform: translateX(-50%);
background-color: #ffffff;
border: 2px solid #00796B;
border-radius: 10px;
padding: 20px;
width: 90%;
max-width: 500px;
box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
text-align: center;
z-index: 1000;
}

.cookie-popup button {
padding: 10px 20px;
margin: 10px 5px 0 5px;
border: none;
border-radius: 5px;
font-size: 15px;
cursor: pointer;
}

.accept-btn {
background-color: #1abc9c;
color: white;
}

.reject-btn {
background-color: #e74c3c;
color: white;
}
</style>
</head>
<body onload="pageLoaded()">

<div class="header">
<img src="./images/header.png" alt="Water Cleaning Banner">
</div>

<nav>
<a href="home.html">Home</a>
<a href="#age-group">Why</a>
<a href="why1.html">Why for Age 10 - 20</a>
<a href="why2.html">Why for Age 21 - 35</a>
<a href="why3.html">Why for Age 36 - 50</a>
<a href="how1.html">How for Age 10 - 20</a>
<a href="how2.html">How for Age 21 - 35</a>
<a href="how3.html">How for Age 36 - 50</a>
</nav>

<main>
<img src="./images/Logo.png" alt="Water Cleaning Logo" style="width: 150px; height: auto;">

<h1>About me</h1>
<h2>Why did I make this website</h2>
<p>I made this website because as a 12 year old I know how hard is it to know the importance of clean water and if we know the importance of clean water we don't know what can we do to clean it that's why to tell you about why and how do we clean water</p>

<h3>Who am I</h3>
<img src="./images/Myphoto.jpeg" alt="A photo of me (Agrim Mandawewala)" style="width: 150px; height: auto;">

<div id="age-group" class="age-group">
<div class="age-box">
<h2>How for Ages 10 - 20</h2>
<button onclick="location.href='how1.html'">Click me</button>
</div>

<div class="age-box">
<h2>How for Ages 20 - 30</h2>
<button onclick="location.href='how2.html'">Click me</button>
</div>

<div class="age-box">
<h2>How for age 30 - 50</h2>
<button onclick="location.href='how3.html'">Click me</button>
</div>
</div>

<address>
Written by Agrim Mandawewala
</address>
</main>

<div class="footer">
<a href="home.html">Home</a>
<a href="why1.html">Why for Age 10 - 20</a>
<a href="why2.html">Why for Age 21 - 30</a>
<a href="why3.html">Why for Age 31 - 45</a>
<a href="how.html">How for Age 10 - 20</a>
</div>

<div id="customPopup" class="cookie-popup">
<p>This website is official and uses cookies. If content is found plagiarised from this website, strong action can be taken.</p>
<button class="accept-btn" onclick="handleChoice('accepted')">Accept All</button>
<button class="reject-btn" onclick="handleChoice('rejected')">Reject All</button>
</div>

<script>
function setCookie(cname, cvalue, exdays) {
const d = new Date();
d.setTime(d.getTime() + (exdays * 24 * 60 * 60 * 1000));
let expires = "expires=" + d.toUTCString();
document.cookie = cname + "=" + cvalue + ";" + expires + ";path=/";
}

function getCookie(cname) {
let name = cname + "=";
let decodedCookie = decodeURIComponent(document.cookie);
let ca = decodedCookie.split(';');
for (let i = 0; i < ca.length; i++) {
let c = ca[i];
while (c.charAt(0) == ' ') {
c = c.substring(1);
}
if (c.indexOf(name) == 0) {
return c.substring(name.length, c.length);
}
}
return "";
}

function checkCookie() {
let user = getCookie("username");
if (user != "") {
alert("Welcome again " + user);
} else {
user = prompt("Please enter your name:", "");
if (user != "" && user != null) {
setCookie("username", user, 365);
}
}
}

function pageLoaded() {
if (getCookie("consent") == "accepted") {
document.getElementById("customPopup").style.display = "none";
checkCookie();
}
}

function handleChoice(choice) {
document.getElementById("customPopup").style.display = "none";
if (choice === "accepted") {
setCookie("consent", "accepted", 365);
checkCookie();
} else {
setCookie("consent", "rejected", 365);
}
}
</script>

</body>
</html>

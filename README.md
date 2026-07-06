<!DOCTYPE html>
<html>
<head>
<title>Special Moment❤️</title>

<meta name="viewport" content="width=device-width, initial-scale=1">

<style>

*{
    box-sizing:border-box;
    font-family:'Poppins',sans-serif;
}

body{
    margin:0;
    height:100vh;
    overflow:hidden;
    background:linear-gradient(135deg,#ff758c,#ff7eb3);
    display:flex;
    justify-content:center;
    align-items:center;
}


.card{

    background:white;
    width:90%;
    max-width:450px;
    padding:30px;
    border-radius:30px;
    text-align:center;
    box-shadow:0 15px 40px #0003;
    z-index:2;

}


h1{
    color:#ff3f6c;
}


button{

    padding:12px 30px;
    border:none;
    border-radius:30px;
    margin:10px;
    font-size:18px;
    cursor:pointer;

}


.yes{

    background:#ff3f6c;
    color:white;

}


.no{

    background:#555;
    color:white;
    position:absolute;

}



input,select{

    width:100%;
    padding:12px;
    margin:10px 0;
    border-radius:15px;
    border:1px solid #ddd;

}


.hidden{
    display:none;
}



.heart{

position:absolute;
color:#fff;
animation:float 8s linear infinite;

}


@keyframes float{

0%{

transform:translateY(100vh);
opacity:1;

}

100%{

transform:translateY(-10vh);
opacity:0;

}

}



.gallery img{

width:30%;
border-radius:15px;
margin:3px;

}


</style>

</head>


<body>


<audio autoplay loop>
<source src="romantic.mp3" type="audio/mpeg">
</audio>



<div class="card">


<!-- PAGE 1 -->

<div id="page1">

<h1 id="typing"></h1>

<p>
I have something special planned for you ❤️
</p>


<button class="yes" onclick="nextPage(2)">
YES 😎
</button>


<button class="no" id="no">
NO 😒
</button>


</div>



<!-- PAGE 2 -->


<div id="page2" class="hidden">


<h1>Yay Madam Ji ❤️</h1>

<p>
Choose our special day ✨
</p>


<input type="date" id="date">


<input type="time" id="time">


<button class="yes" onclick="nextPage(3)">
Next ➜
</button>


</div>




<!-- PAGE 3 -->


<div id="page3" class="hidden">


<h1>Food Time 🍽️</h1>


<label>
<input type="radio" name="food" value="Pizza">
🍕 Pizza
</label>

<br>


<label>
<input type="radio" name="food" value="Burger">
🍔 Burger
</label>

<br>


<label>
<input type="radio" name="food" value="Pasta">
🍝 Pasta
</label>

<br>


<label>
<input type="radio" name="food" value="Rameen Special ❤️">
🍜🥵 Rameen Special
</label>


<br>


<button class="yes" onclick="finish()">
Confirm 💖
</button>


</div>




<!-- PAGE 4 -->


<div id="page4" class="hidden">


<h1>
Date Confirmed ❤️
</h1>


<div class="gallery">

<img src="photos/photo1.jpg">
<img src="photos/photo2.jpg">
<img src="photos/photo3.jpg">

</div>


<p id="final"></p>


<h2>
I can't wait to see you Rifa mam 😉
</h2>


<div id="countdown"></div>


</div>


</div>





<script>


// typing effect


let text="Hello Mam, Will You Go On A Date With Me? 🙄";

let i=0;


function typing(){

if(i<text.length){

document.getElementById("typing").innerHTML += text.charAt(i);

i++;

setTimeout(typing,80);

}

}


typing();




// no button escape


let no=document.getElementById("no");


no.onmouseover=function(){

no.style.left=Math.random()*80+"vw";

no.style.top=Math.random()*80+"vh";

}




// page change


function nextPage(page){

document.querySelectorAll(".card > div").forEach(x=>{
x.classList.add("hidden");
});


document.getElementById("page"+page)
.classList.remove("hidden");

}




function finish(){


let food=document.querySelector(
'input[name="food"]:checked'
);


if(!food){

alert("Choose food for Rameen ❤️");
return;

}


let date=document.getElementById("date").value;

let time=document.getElementById("time").value;



nextPage(4);



document.getElementById("final").innerHTML=

`
Date: ${date}<br>
Time: ${time}<br>
Food: ${food.value}
`;

startCountdown(date);



}



// countdown


function startCountdown(date){

let target=new Date(date).getTime();


setInterval(function(){


let now=new Date().getTime();

let gap=target-now;


let days=Math.floor(
gap/(1000*60*60*24)
);


document.getElementById("countdown").innerHTML=

"Only "+days+" days left ❤️";


},1000);


}





// hearts


setInterval(()=>{


let heart=document.createElement("div");

heart.className="heart";

heart.innerHTML="❤️";


heart.style.left=Math.random()*100+"vw";

heart.style.fontSize=
20+Math.random()*30+"px";


document.body.appendChild(heart);



setTimeout(()=>{

heart.remove();

},8000);


},400);



</script>


</body>
</html>

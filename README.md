<!DOCTYPE html>
<html lang="vi">

<head>
<meta charset="UTF-8">
<title>Dành Tặng Em ❤️</title>

<style>

body{
font-family:Arial;
text-align:center;
background:linear-gradient(135deg,#ff9ecf,#ffc0cb);
overflow:hidden;
}

/* box */

.box{
margin-top:120px;
}

/* input */

input{
padding:10px;
font-size:18px;
width:80px;
margin:5px;
text-align:center;
border-radius:10px;
border:none;
}

/* button */

button{
padding:12px 20px;
font-size:18px;
margin:10px;
border:none;
border-radius:12px;
background:#ff4da6;
color:white;
cursor:pointer;
}

button:hover{
background:#ff1a8c;
}

#page2,#page3,#letterPage{
display:none;
}

/* ================= */
/* TRÁI TIM BAY */
/* ================= */

.heart{
position:absolute;
color:#ff2d75;
animation:float 6s linear infinite;
}

@keyframes float{

0%{
transform:translateY(0);
opacity:1;
}

100%{
transform:translateY(-100vh);
opacity:0;
}

}

/* ================= */
/* BỨC THƯ */
/* ================= */

.letter{
width:320px;
background:white;
padding:30px;
border-radius:15px;
margin:auto;
box-shadow:0 10px 30px rgba(0,0,0,0.2);
animation:openLetter 1s;
}

@keyframes openLetter{
from{transform:scale(0)}
to{transform:scale(1)}
}

/* ================= */
/* HOA HỒNG */
/* ================= */

.rose{
position:relative;
width:80px;
height:80px;
margin:30px auto;
}

.petal{
position:absolute;
width:45px;
height:45px;
background:#ff0033;
border-radius:50%;
}

.petal:nth-child(1){top:0;left:18px;}
.petal:nth-child(2){top:18px;left:0;}
.petal:nth-child(3){top:18px;left:36px;}
.petal:nth-child(4){top:36px;left:18px;}

.stem{
width:6px;
height:90px;
background:green;
margin:auto;
border-radius:3px;
}

/* sparkle */

.sparkle{
position:absolute;
color:white;
animation:sparkle 3s linear infinite;
}

@keyframes sparkle{
0%{opacity:0}
50%{opacity:1}
100%{opacity:0}
}

</style>
</head>


<body>

<!-- TIM -->

<div class="heart" style="left:10%;font-size:25px;">❤</div>
<div class="heart" style="left:30%;font-size:20px;">❤</div>
<div class="heart" style="left:50%;font-size:30px;">❤</div>
<div class="heart" style="left:70%;font-size:22px;">❤</div>
<div class="heart" style="left:90%;font-size:26px;">❤</div>


<!-- PAGE 1 -->

<div id="page1" class="box">

<h2>Ngày đặc biệt? 💖</h2>

<input id="day" placeholder="Ngày">
<input id="month" placeholder="Tháng">
<input id="year" placeholder="Năm">

<br>

<button onclick="checkDate()">Xác nhận</button>

<p id="error" style="color:red;"></p>

</div>


<!-- PAGE 2 -->

<div id="page2" class="box">

<h2>Vậy bạn có yêu anh ấy hông? 😳</h2>

<button onclick="next()">A. Cóoo rất nhiều</button><br>
<button onclick="next()">B. Cực kì yeeuuu</button><br>
<button onclick="next()">C. Yêu vãi chưởng</button><br>
<button onclick="next()">D. Chọn cả 3 đáp án trên</button>

</div>


<!-- PAGE 3 -->

<div id="page3" class="box">

<h2>💌 Anh có lá thư cho em</h2>

<button onclick="openLetter()">Mở thư</button>

</div>


<!-- LETTER PAGE -->

<div id="letterPage" class="box">

<div class="letter">

<h2>Gửi em ❤️</h2>

<p>
Từ ngày em xuất hiện trong cuộc đời anh,  
mọi thứ trở nên đẹp hơn rất nhiều.  

Cảm ơn em vì đã ở bên anh,  
cảm ơn vì đã yêu anh.

Anh hy vọng chúng ta sẽ cùng nhau đi thật xa.  
</p>

<!-- HOA -->

<div class="rose">

<div class="petal"></div>
<div class="petal"></div>
<div class="petal"></div>
<div class="petal"></div>

</div>

<div class="stem"></div>

<h3>Bông hoa này dành cho em 🌹</h3>

<p>Anh yêu em rất nhiều ❤️</p>

</div>

</div>


<script>

/* CHECK DATE */

function checkDate(){

let d=document.getElementById("day").value;
let m=document.getElementById("month").value;
let y=document.getElementById("year").value;

/* CHỈNH NGÀY Ở ĐÂY */

if(d=="08" && m=="02" && y=="2026"){

document.getElementById("page1").style.display="none";
document.getElementById("page2").style.display="block";

}else{

document.getElementById("error").innerHTML="Sai rồi thử lại đi 😝";

}

}

/* PAGE 2 -> PAGE 3 */

function next(){

document.getElementById("page2").style.display="none";
document.getElementById("page3").style.display="block";

}

/* OPEN LETTER */

function openLetter(){

document.getElementById("page3").style.display="none";
document.getElementById("letterPage").style.display="block";

createHearts();

}

/* TIM BAY */

function createHearts(){

setInterval(()=>{

let heart=document.createElement("div");

heart.className="heart";
heart.innerHTML="❤";

heart.style.left=Math.random()*100+"vw";
heart.style.fontSize=(Math.random()*20+15)+"px";

document.body.appendChild(heart);

setTimeout(()=>{
heart.remove();
},6000);

},400);

}

</script>

</body>
</html>

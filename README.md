<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Visual Card</title>

<style>
*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:Inter,Arial,sans-serif;
}

body{
background:linear-gradient(180deg,#031522,#0b4f83);
min-height:100vh;
padding:20px;
color:white;
}

.header{
text-align:center;
margin-bottom:25px;
}

.header h1{
font-size:34px;
}

.wallet{
backdrop-filter:blur(20px);
background:rgba(255,255,255,.08);
border:1px solid rgba(255,255,255,.2);
padding:20px;
border-radius:25px;
margin-bottom:20px;
}

.wallet h2{
font-size:15px;
opacity:.8;
}

.wallet h1{
font-size:35px;
margin-top:10px;
}

.cards{
display:flex;
overflow:auto;
gap:20px;
padding-bottom:10px;
}

.card{
min-width:330px;
height:200px;
padding:25px;
border-radius:25px;
position:relative;
cursor:pointer;
box-shadow:0 10px 30px rgba(0,0,0,.3);
}

.usa{
background:linear-gradient(135deg,#1453ff,#35b8ff);
}

.uk{
background:linear-gradient(135deg,#3417a8,#8037ff);
}

.flag{
font-size:28px;
}

.type{
margin-top:10px;
font-size:13px;
opacity:.8;
}

.balance{
margin-top:20px;
font-size:30px;
font-weight:bold;
}

.number{
margin-top:25px;
letter-spacing:3px;
}

.owner{
margin-top:10px;
font-size:14px;
}

.actions{
display:grid;
grid-template-columns:repeat(2,1fr);
gap:15px;
margin-top:25px;
}

button{
padding:15px;
border:none;
border-radius:20px;
cursor:pointer;
font-size:16px;
font-weight:bold;
background:rgba(255,255,255,.15);
color:white;
backdrop-filter:blur(20px);
}

.transactions{
margin-top:25px;
background:rgba(255,255,255,.08);
backdrop-filter:blur(20px);
padding:20px;
border-radius:25px;
border:1px solid rgba(255,255,255,.15);
}

.tx{
display:flex;
justify-content:space-between;
padding:15px 0;
border-bottom:1px solid rgba(255,255,255,.1);
}

.status{
position:absolute;
top:20px;
right:20px;
background:rgba(255,255,255,.2);
padding:8px 12px;
border-radius:20px;
}

.modal{
display:none;
position:fixed;
inset:0;
background:rgba(0,0,0,.8);
justify-content:center;
align-items:center;
}

.modal-box{
width:90%;
max-width:400px;
padding:25px;
border-radius:25px;
background:rgba(255,255,255,.1);
backdrop-filter:blur(25px);
}

.close{
margin-top:15px;
width:100%;
}
</style>
</head>

<body>

<div class="header">
<h1>VISUAL CARD</h1>
<p>USA & UK Virtual Cards</p>
</div>

<div class="wallet">
<h2>Total Wallet Balance</h2>
<h1 id="wallet">$2,100.00</h1>
</div>

<div class="cards">

<div class="card usa" onclick="openCard('USA Virtual USD Card','$1,250.00','Visa','United States')">

<div class="flag">🇺🇸</div>

<div class="status">ACTIVE</div>

<div class="type">USA Virtual USD Card</div>

<div class="balance">$1,250.00</div>

<div class="number">
**** **** **** 4532
</div>

<div class="owner">
John Smith
</div>

</div>

<div class="card uk" onclick="openCard('UK Virtual GBP Card','£850.00','Mastercard','United Kingdom')">

<div class="flag">🇬🇧</div>

<div class="status">ACTIVE</div>

<div class="type">UK Virtual GBP Card</div>

<div class="balance">£850.00</div>

<div class="number">
**** **** **** 7821
</div>

<div class="owner">
Sarah Williams
</div>

</div>

</div>

<div class="actions">

<button onclick="alert('Create Card')">
➕ Create Card
</button>

<button onclick="alert('Fund Card')">
💳 Fund Card
</button>

<button onclick="alert('Withdraw')">
💸 Withdraw
</button>

<button onclick="alert('Freeze Card')">
❄ Freeze Card
</button>

</div>

<div class="transactions">

<h2>Recent Transactions</h2>

<div class="tx">
<span>Netflix</span>
<span>-$15.99</span>
</div>

<div class="tx">
<span>Amazon Gift Card</span>
<span>-$50.00</span>
</div>

<div class="tx">
<span>Wallet Deposit</span>
<span>+$500.00</span>
</div>

<div class="tx">
<span>Apple Gift Card</span>
<span>-$25.00</span>
</div>

</div>

<div class="modal" id="modal">

<div class="modal-box">

<h2 id="cardName"></h2>

<br>

<p><b>Country:</b> <span id="country"></span></p>

<p><b>Network:</b> <span id="network"></span></p>

<p><b>Balance:</b> <span id="amount"></span></p>

<p><b>Status:</b> Active</p>

<p><b>Number:</b> **** **** **** 1234</p>

<button class="close" onclick="closeCard()">
Close
</button>

</div>

</div>

<script>

function openCard(name,balance,network,country){

document.getElementById("modal").style.display="flex";

document.getElementById("cardName").innerHTML=name;

document.getElementById("amount").innerHTML=balance;

document.getElementById("network").innerHTML=network;

document.getElementById("country").innerHTML=country;

}

function closeCard(){

document.getElementById("modal").style.display="none";

}

</script>

</body>
</html>

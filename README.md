<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Visual Card</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial,sans-serif;
}

body{
    background:linear-gradient(180deg,#061c2f,#0a4a75);
    min-height:100vh;
    color:white;
}

.header{
    text-align:center;
    padding:20px;
    font-size:30px;
    font-weight:bold;
}

.container{
    padding:20px;
}

.glass{
    backdrop-filter:blur(20px);
    background:rgba(255,255,255,0.12);
    border:1px solid rgba(255,255,255,0.2);
    border-radius:25px;
    box-shadow:0 8px 30px rgba(0,0,0,.2);
}

.card{
    padding:25px;
    margin-bottom:20px;
    cursor:pointer;
    transition:0.3s;
}

.card:hover{
    transform:scale(1.02);
}

.country{
    display:flex;
    justify-content:space-between;
    margin-bottom:20px;
}

.balance{
    font-size:32px;
    font-weight:bold;
}

.number{
    margin-top:20px;
    letter-spacing:3px;
}

.buttons{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:10px;
}

button{
    padding:15px;
    border:none;
    border-radius:15px;
    background:#00d4ff;
    color:white;
    font-size:16px;
    cursor:pointer;
}

.transactions{
    margin-top:20px;
    padding:20px;
}

.transaction{
    display:flex;
    justify-content:space-between;
    padding:12px 0;
    border-bottom:1px solid rgba(255,255,255,0.2);
}

.modal{
    position:fixed;
    inset:0;
    background:rgba(0,0,0,.7);
    display:none;
    justify-content:center;
    align-items:center;
}

.modal-content{
    width:90%;
    max-width:350px;
    padding:20px;
}
</style>
</head>
<body>

<div class="header">
    VISUAL CARD
</div>

<div class="container">

    <div class="card glass" onclick="showCard()">

        <div class="country">
            <span>🇺🇸 USA CARD</span>
            <span>VIRTUAL</span>
        </div>

        <div class="balance" id="balance">$500</div>

        <div class="number">
            **** **** **** 1234
        </div>

        <br>

        <div>
            John Customer
        </div>

    </div>

    <div class="buttons">
        <button onclick="buyCard()">
            Buy Card
        </button>

        <button onclick="spendMoney()">
            Spend $10
        </button>
    </div>

    <div class="transactions glass">
        <h3>Transactions</h3>

        <div id="history">

            <div class="transaction">
                <span>Card Created</span>
                <span>$500</span>
            </div>

        </div>

    </div>

</div>

<div class="modal" id="modal">
    <div class="modal-content glass">

        <h2>Card Details</h2>

        <br>

        <p>Country: USA</p>
        <p>Type: Virtual Visa</p>
        <p>Card Number: 4531 2234 9988 1234</p>
        <p>Expiry: 10/30</p>

        <br>

        <button onclick="closeCard()">
            Close
        </button>

    </div>
</div>

<script>

let balance = 500;

function updateBalance(){
    document.getElementById("balance").innerHTML =
        "$" + balance;
}

function buyCard(){

    balance += 100;

    updateBalance();

    addHistory("Card Funded","+$100");
}

function spendMoney(){

    if(balance < 10){
        alert("Insufficient funds");
        return;
    }

    balance -= 10;

    updateBalance();

    addHistory("Purchase","-$10");
}

function addHistory(title,amount){

    document.getElementById("history").innerHTML += `
    <div class="transaction">
        <span>${title}</span>
        <span>${amount}</span>
    </div>`;
}

function showCard(){
    document.getElementById("modal").style.display="flex";
}

function closeCard(){
    document.getElementById("modal").style.display="none";
}

</script>

</body>
</html>

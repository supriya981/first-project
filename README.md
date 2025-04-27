# first-project
html code
<html>
<head>
<title>Game</title>
<style>
body{
	text-align: center;
	font-family: Arial, sans-serif;
}
.game-container{
	display:flex;
	justify-content: center;
	gap: 20px;
	margin-top: 20px;
}
.card{
	width: 100px;
	height: 150px;
	background-color:gray;
	display:flex;
	align-items:center;
	font-size: 24px;
	font-weight: bold;
	color: white;
	cursor: pointer;
}
.hidden{
	background-color: black;
	color:black;
}
.message{
	margin-top: 20px;
	font-size:18px;
}
</style>
</head>
<body>
	<h2>Card Gussing Game</h2>
	<p>Click "Shuffle" and ry to find the Ace!</p>
<div class="game-container">
	<div class="class hidden" id="card1" onclick="guessCard(1)">?</div>
	<div class="class hidden" id="card2" onclick="guessCard(2)">?</div>
</div>
<p class="message" id="message"></p>
<button onclick="shuffleCards()">Shuffle</button>
<script>
	let correctCard=1;
	function shuffleCards(){
		document.getElementById("message").textContent="?";
		correctCard = Math.random()<0.5 ? 1:2;
		document.getElementById("card1").textContent="?";
		document.getElementById("card2").textContent="?";
		document.getElementById("card1").classList.add=("hidden");
		document.getElementById("card2").classList.add=("hidden");
}

function guessCard(selectedCard){
	let message = document.getElementById("message");
	if(selectedCard===correctCard){
		message.textContent="Correct! You have found an Ace.";
		message.style.color="green";
		}
	else{
		message.textContent="Wrong! Try Again.";
		message.style.color="red";
		}
	document.getElementById("card1").textContent = correctCard === 1?"A":"X";
	document.getElementById("card2").textContent = correctCard === 2?"A":"X";
}
</script>
</body>
</html>

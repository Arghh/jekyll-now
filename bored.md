---
layout: default
---
<head><script type="text/javascript"></script>
<title>ROCK,PAPER,SCISSORS</title>
</head>
<body>
<h1>Bored?</h1>
<p>Game is: Rock, Paper, Scissors. Just type in your choice</p>
<div>
<button onClick="playFunction();"> START THE GAME </button>
<p class="comp">Computer picks <span id="computerpicks" style="color:red"></span></p>
<p><span id="result">Result</span></p>
<p><span>Wins: </span><span id="wins"></span><br>
   <span>Losses: </span><span id="losses"></span><br>
   <span>Draws: </span><span id="ties"></span><br>
</div>
<script>
var win = 0;
var loss = 0;
var tie = 0;
function playFunction() {   
var userChoice = prompt("Do you choose rock, paper or scissors?");
var computerChoice = Math.random();
if (computerChoice < 0.34) {
    computerChoice = "rock";
} else if(computerChoice <= 0.67) {
    computerChoice = "paper";
} else {
    computerChoice = "scissors";
}
var computerpicks = document.getElementById('computerpicks');
computerpicks.innerHTML = computerChoice;
document.getElementById("wins").innerHTML = win;
document.getElementById("losses").innerHTML = loss;
document.getElementById("ties").innerHTML = tie; 
var result = document.getElementById("result");

var compare = function(choice1, choice2) {
    if(choice1 === choice2) {
        document.getElementById("result").innerHTML = "It's a tie!";
        tie = tie + 1;
    } else if (choice1 === "rock") {
            if(choice2 === "scissors") {
        document.getElementById("result").innerHTML = "You Win!";
        win = win + 1;
    } else {
        if(choice2 === "paper")
        document.getElementById("result").innerHTML = "You Loose";
        loss = loss + 1;
    }
}
    if(choice1 === "paper") {
    if(choice2 === "rock") {
        document.getElementById("result").innerHTML = "You Win!";
        win = win + 1;
    } else {
        if(choice2 === "scissors") {
            document.getElementById("result").innerHTML = "You Loose";
            loss = loss + 1;
    }
}
    if(choice1 === "scissors") {
    if(choice2 === "paper") {
        document.getElementById("result").innerHTML = "You Win!";
        win = win + 1;
    } else {
        if(choice2 === "rock") {
           document.getElementById("result").innerHTML = "You Loose";
           loss = loss + 1;
        }
    }
}
}
}
console.log("User Choice: " + userChoice);
console.log("Computer Choice: " + computerChoice);
compare(userChoice, computerChoice)
} 

</script>
</body>
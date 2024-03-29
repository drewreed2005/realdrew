---
title: Blackjack Frontend Conversion
layout: none
description: Try it out!
permalink: /bjhead
hide: true
search-exclude: true
---
<style>
    .big_ol_cont {
        justify-content:center;
        margin:auto;
        border:20px solid;
        border-color:black;
        border-radius:200px;
        background-color: #5AB067;
        font-family:serif;
    }

    .card_table_d {
        width: 1000px;
        height: 300px;
        border: 10px solid;
        border-radius: 150px;
        background-color: #FF5D5D;
        padding:20px;
        justify-content:center;
        text-align:center;
        font-size:16px;
    }

    .card_table_p {
        width: 1000px;
        height: 300px;
        border: 10px solid;
        border-radius: 150px;
        background-color: white;
        padding:20px;
        justify-content:center;
        text-align:center;
        font-size:16px;
    }

    .select_table {
        margin:auto;
        text-align:center;
        justify-content:center;
        padding:5px;
        font-family:serif;
    }

    .db_input {
        justify-content:center;
        margin:auto;
        border: 5px solid;
        border-radius: 10px;
        background-color:white;
    }

    .select_button {
        margin:auto;
        text-align:center;
        justify-content:center;
        border: 5px solid;
        border-radius:5px;
        width:120px;
        height:60px;
        background-color:white;
        font-size:14px;
        font-family:serif;
    }

    table { margin: auto }
</style>

<div class="big_ol_cont">
    <br>
    <div style="text-align:center;justify-content:center">
        <h2>Dealer Hand</h2>
        <table id="dealer_card_table" class="card_table_d">
            <tr id="dealer_cards">
            </tr>
        </table>
        <h2>Player Hand</h2>
        <table id="dealer_card_table" class="card_table_p">
            <tr id="player_cards">
            </tr>
        </table>
    </div>
    <div id="buttons" style="margin:auto;text-align:center;justify-content:center">
        <br>
        <div id="result_text"></div>
        <br>
        <button id="hit_button" class="select_button" style="display:none" onclick="buttonHit()">Hit</button><button id="stay_button" class="select_button" style="display:none" onclick="dealerTurn()">Stay</button>
        <button id="play_again" class="select_button" style="display:block" onclick="gameStart()">Play</button><button id="finish_game" class="select_button" style="display:none" onclick="record()">Finish and Submit Score</button>
        <input id="username_input" class="db_input" type="text" style="display:none"><button id="submit_button" class="select_button" style="display:none">Submit</button>
    </div>
    <br>
</div>

<script>
    const dealerRow = document.getElementById("dealer_cards");
    const playerRow = document.getElementById("player_cards");
    const hitButton = document.getElementById("hit_button");
    const stayButton = document.getElementById("stay_button");
    const playButton = document.getElementById("play_again");
    const finishButton = document.getElementById("finish_game");
    const usernameInput = document.getElementById("username_input");
    const resultBox = document.getElementById("result_text");
    const submitButton = document.getElementById("submit_button");

    // card class
    class Card {
        constructor(suit, val) {
            this.suit = suit;
            this.value = val;
            if (val == 11) {
                this.kind = "Ace";
            } else if (val == 12) {
                this.kind = "Jack";
            } else if (val == 13) {
                this.kind = "Queen";
            } else if (val == 14) {
                this.kind = "King";
            } else {
                this.kind = String(val);
            }
        };
        cshow() {
            return this.kind + " of " + this.suit;
        };
        adjustAce() {
            if (this.kind == "Ace") {
                this.value = 1;
            }
        };
    };

    // card test
    var tcard = new Card("Spades", 3);
    console.log(tcard.cshow());

    // deck class
    class Deck {
        constructor() {
            this.cards = [];
            this.build()
        }
        build() {
            const suits = ["Spades", "Hearts", "Diamonds", "Clubs"];
            for (let s in suits) {
                for (let v = 2; v < 15; v++) {
                    this.cards.push(new Card(suits[s], v));
                }
            }
        };
        shuffle() {
            for (var i = this.cards.length - 1; i > 0; i--) {
                var j = Math.floor(Math.random() * (i + 1));
                var temp = this.cards[i];
                this.cards[i] = this.cards[j];
                this.cards[j] = temp;
            }
        }
        draw() {
            return this.cards.pop();
        }
    };

    // deck test
    var tdeck = new Deck();
    tdeck.shuffle();
    console.log(tdeck.cards);

    function givePlayerCard(card) {
        const newCard = document.createElement("td");
        newCard.innerHTML = card.kind + " of " + card.suit;
        playerRow.appendChild(newCard);
    };

    function giveDealerCard(card) {
        if (card != "face_down") {
            const newCard = document.createElement("td");
            newCard.innerHTML = card.kind + " of " + card.suit;
            dealerRow.appendChild(newCard);
        } else {
            const newCard = document.createElement("td");
            newCard.innerHTML = "Face-Down Card";
            newCard.id = "facedown_card";
            dealerRow.appendChild(newCard);
        }
    };

    //initiating globals
    var currentStreak = 0;
    var playerHand = [];
    var dealerHand = [];
    var deck = new Deck();
    var d2 = "secret";

    function gameStart() {
        hitButton.style = "display:none";
        stayButton.style = "display:none";
        playButton.style = "display:none";
        finishButton.style = "display:none";
        resultBox.innerHTML = "";
        playerHand = [];
        dealerHand = [];
        dealerRow.innerHTML = "";
        playerRow.innerHTML = "";
        deck = new Deck();
        deck.shuffle();

        console.log("Initial draws:"); // giving the initial draws
        var d1 = dealerHit();
        giveDealerCard(d1);
        console.log("The dealer draws: " + d1);
        var p1 = playerHit()
        console.log("You receive: " + p1);
        givePlayerCard(p1);
        d2 = dealerHit();
        giveDealerCard("face_down");
        console.log("The dealer draws a face-down card...");
        var p2 = playerHit();
        console.log("You receive: " + p2);
        givePlayerCard(p2)
        console.log(playerHand);
        if (takesum(playerHand) == 21) { // instant player win on blackjack potentially
            if (takesum(dealerHand) != 21) {
                console.log("WOW! A blackjack! You win!");
                win();
                return;
            } else {
                console.log("Both you and the dealer have blackjack. It's a push! Your streak stays the same.");
                fpush();
                return;
            }
        };
        console.log("--------------------------------")
        console.log("Dealer's hand: " + d1 + ", ???")
        playerTurn() // once player turn finishes, the dealer turn occurs
    };

    function takesum(hand) {
        let sm = 0;
        for (let i = 0; i < hand.length; i++) {
            var pcard = hand[i];
            if (pcard.value > 11) {
                sm = sm + 10;
            } else {
                sm = sm + pcard.value;
            };
        };
        if (sm > 21) {
            for (let i = 0; i < hand.length; i++) {
                var pcard = hand[i];
                if (pcard.value == 11) {
                    pcard.adjustAce();
                    return takesum(hand);
                };
            };
        };
        console.log(sm)
        return sm
    };

    function playerHit() {
        var res = deck.draw();
        if ((res.value == 11) && (takesum(playerHand) + 11 > 21)) { // adjusting ace if it would break
            res.adjustAce();
        };
        playerHand.push(res);
        return res
    }

    function buttonHit() {
        var res = deck.draw();
        if ((res.value == 11) && (takesum(playerHand) + 11 > 21)) { // adjusting ace if it would break
            res.adjustAce();
        };
        playerHand.push(res);
        givePlayerCard(res);
        playerTurn();
    }

    function dealerHit() {
        var res = deck.draw();
        if ((res.value == 11) && (takesum(dealerHand) + 11 > 21)) { // adjusting ace if it would break
            res.adjustAce();
        };
        dealerHand.push(res);
        return res
    }

    function handDisplay(hand) {
        var disp_hand = [];
        for (let i = 0; i < hand.length; i++) {
            var thisCard = hand[i];
            var shown = thisCard.kind + " of " + thisCard.suit;
            disp_hand.push(shown);
        };
        return disp_hand;
    };

    function playerTurn() {
        console.log("Your hand: " + String(handDisplay(playerHand)));
        if (takesum(playerHand) > 21) {
            console.log("You break! You lose.");
            lose();
            return
        };
        hitButton.style = "display:block";
        stayButton.style = "display:block";
    }

    function dealerTurn() {
        hitButton.style = "display:none";
        stayButton.style = "display:none";
        console.log("Dealer's hand: " + String(handDisplay(dealerHand)));
        document.getElementById("facedown_card").innerHTML = d2.kind + " of " + d2.suit;
        if (takesum(dealerHand) > 16) {
            console.log("The dealer stays.");
        } else {
            var dealDraw = dealerHit();
            giveDealerCard(dealDraw);
            if (takesum(dealerHand) > 21) {
                console.log("The dealer breaks! You win.");
                win();
                return;
            }
            dealerTurn();
            return;
        };
        if (takesum(playerHand) > takesum(dealerHand)) {
            console.log("Congratulations! You won with a hand worth " + String(takesum(playerHand)) + "!");
            win();
        } else if (takesum(dealerHand) > takesum(playerHand)) {
            console.log("Too bad! You lost to the dealer's hand, worth "  + String(takesum(dealerHand)) + "!");
            lose();
        } else {
            console.log("It's a push! You keep your streak.");
            fpush();
        };
        return
    }

    function win() {
        hitButton.style = "display:none";
        stayButton.style = "display:none";
        currentStreak += 1;
        resultBox.innerHTML = "Congratulations! You won.";
        playButton.innerHTML = "Play Again";
        playButton.style = "display:block";
        finishButton.style = "display:block";
        return
    }
    function lose() {
        hitButton.style = "display:none";
        stayButton.style = "display:none";
        currentStreak = 0;
        resultBox.innerHTML = "Oh no! You lost.";
        playButton.innerHTML = "Play Again";
        playButton.style = "display:block";
        return
    }

    function fpush() {
        hitButton.style = "display:none";
        stayButton.style = "display:none";
        resultBox.innerHTML = "It's a push! You keep your streak.";
        playButton.innerHTML = "Play Again";
        playButton.style = "display:block";
        finishButton.style = "display:block";
        return
    }

    function record() {
        playButton.style = "display:none";
        finishButton.style = "display:none";
        usernameInput.style = "display:block";
        resultBox.innerHTML = "Input a username for the leaderboard. (Current Streak: " + String(currentStreak) + ")";
        submitButton.style = "display:block";
        console.log(String(currentStreak));
    }
</script>
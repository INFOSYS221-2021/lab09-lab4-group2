# lab09-lab4-group12
lab09-lab4-group12 created by GitHub Classroom
Names:
- Helen Vincent 
- Bao Li

Exercise One: Understand Deck of Cards

1. GET is one of the HTTP request methods. What is a GET method? Give an example of how you can use GET with the Deck Of Cards API.
Get is used to request data from a specified resource. GET deck_ID

2. List all available features that you can use from Deck of Cards. For example, one of the APIs you can use is to shuffle cards.

Shuffle cards, reshuffle cards, draw a card,  get a new deck, add to piles, reshuffle piles, list cards in pile, draw from pile, partial deck. 

3. What is the API for getting a brand new deck that also includes two jokers?

https://deckofcardsapi.com/api/deck/new/?jokers_enabled=true

 How many cards are drawn from the deck? What are the cards?

Two, KH, 8C

How do you retrieve deck_id from the response? Write your code using JavaScript.

fetch("https://deckofcardsapi.com/api/deck/new/shuffle/?deck_count=1")
      .then(response => response.json())
      .then(data => {
          // handle the response
          deckID = data.deck_id;
          console.log(deckID);
      })
      .catch(error => {
          // handle the error
          console.log('There has been an error');
      });

	return

How do you print information about each card? Write your code using JavaScript
_.values(cards)

Exercise Two: Complete Hit Me! Game with Deck of Cards API: 

 TODO 1: use the appropriate API to shuff

fetch('https://deckofcardsapi.com/api/deck/new/shuffle/?deck_count=1');

 TODO 2: get the id of the deck from
 
    deckID = data.deck_id;
    return deckID;
    
TODO 3: use the appropriate API to draw one card 
from the deck created at the start of the game
Hint: use the variable thisDeck

let response = await fetch('https://deckofcardsapi.com/api/deck/' + thisDeck + '/draw/?count=1');

TODO 4: find the value and suit of the card 

let cardValue =cardInfo.cards[0].value;

let cardSuit = cardInfo.cards[0].suit;


TODO 5: update the cardValue appropriately

  if (cardValue == 'JACK') {
    cardValue = 11;
  }
  else if (cardValue == 'QUEEN') {
    cardValue = 12;
  } 
  else if (cardValue == 'KING') {
    cardValue = 13;
  }
  else if (cardValue == 'ACE') {
    cardValue = 1;
  }
  

TODO 6: find the image of the card

let imgUrl = cardInfo.cards[0].image


COMPLETE THING:

<h1>Hit Me!</h1>
<div>
  Try to get the total value of your cards closer to zero within 5 hits!
</div>
<h3>How to play</h3>
<div>
  <ul>
    <li>Click "Hit Me!" to get a card</li>
    <li>Each card has a value. Aces count as 1, Jacks count as 11, Queens count as 12, and Kings count as 13.</li>
    <li>Black cards are added to the total. Red cards are substracted from the total.</li>
    <li>You may take up to 5 hits</li>
  </ul>
</div>
<div>
  <input type="button" id="hitMeBtn" value="Hit Me!">
  <input type="button" id="restartBtn" value="Restart" disabled="disabled">
</div>
<hr />
<div id="hitMeSum">
  Click Hit Me! to start playing!
</div>
<div id="hitMeCards">

</div>





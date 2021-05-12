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

Exercise Two: Complete Hit Me! Game with Deck of Cards API: 

 TODO 1: use the appropriate API to shuff

fetch('https://deckofcardsapi.com/api/deck/new/shuffle/?deck_count=1');

 TODO 2: get the id of the deck from
 
    deckID = data.deck_id;
    return deckID;
    
TODO 3: use the appropriate API to draw one card 
from the deck created at the start of the game
Hint: use the variable thisDec


TODO 4: find the value and suit of the card 


TODO 5: update the cardValue appropriately
if card is Jack, then set the cardValue to 11, etc

TODO 6: find the image of the card







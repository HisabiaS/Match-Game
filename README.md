# Match Game 🎴

## Contents

-   Introduction
-   Deliverable
-   Functions I Implemented

------------------------------------------------------------------------

## Introduction

This is a simple memory-based **Match Game** I built for my portfolio
project. The game is played with 12 cards (6 pairs), each showing an
image when flipped. The main goal is to match all pairs while keeping
track of the number of flips and matches.

I wrote the JavaScript logic to handle creating cards, shuffling images,
keeping score, and resetting the game. The project helped me practice
working with the DOM, using helper libraries like **Underscore.js**, and
organizing game state with objects.

------------------------------------------------------------------------

## Deliverable

### 1. `createNewCard()`

Creates and returns a new DOM element that represents a card. The card
has two sides (front and back), and I structured it as:

``` html
<div class="card">
  <div class="card-down"></div>
  <div class="card-up"></div>
</div>
```

This just builds the card element but doesn't place it in the DOM yet.

------------------------------------------------------------------------

### 2. `appendNewCard(parentElement)`

Takes a parent element (like the card container) and adds a newly
created card to it. This is what actually makes the card show up on the
page.

------------------------------------------------------------------------

### 3. `shuffleCardImageClasses()`

Uses **Underscore.js** to shuffle an array of image classes (`image-1`
through `image-6`), making sure there are two of each. This ensures the
cards are randomized each time the game starts.

------------------------------------------------------------------------

### 4. `createCards(parentElement, shuffledImageClasses)`

Generates all 12 cards, attaches them to the DOM, assigns each a
shuffled image class, and stores them as custom card objects.
Each card object contains:

-   `index` → position in the loop
-   `element` → the actual DOM element
-   `imageClass` → the image class applied

This made it easy to track cards in the JavaScript logic.

------------------------------------------------------------------------

### 5. `doCardsMatch(cardObject1, cardObject2)`

Compares two card objects and returns `true` if their `imageClass`
values match, otherwise `false`.

------------------------------------------------------------------------

### 6. `incrementCounter(counterName, parentElement)`

Updates the game counters (flip count and match count). I used a global
`counters` object to store the values and updated the DOM whenever a
counter changed.

------------------------------------------------------------------------

### 7. `onCardFlipped(newlyFlippedCard)`

Handles the main game logic whenever a card is flipped:

-   Increments the flip counter.
-   If it's the first card, it stores it.
-   If it's the second card, it checks for a match:
    -   If they don't match, both cards flip back.
    -   If they do match, the match counter goes up, and a sound effect
        plays.
-   If all matches are found, a win sound plays.

------------------------------------------------------------------------

### 8. `resetGame()`

Resets everything back to the starting state: clears the cards, resets
counters, sets `lastCardFlipped` to null, and starts a new shuffled
game.

------------------------------------------------------------------------

## Included Function

-   **`setUpGame()`** -- Provided starter code that creates the game by
    calling my `createCards()` function and attaching click events to
    each card.

------------------------------------------------------------------------

✨ This project was a great exercise in DOM manipulation, game logic,
and organizing state with objects. It also gave me practice with helper
libraries like Underscore.js.

# FlashCards Starter Kit

## Module 2 : Solo Project : Virginia Ladd

## About the Project

This is the first project of Module 2. We were instructed to clone down a repo of https://github.com/turingschool-examples/flashcards-starter and edit to make the 'game' work. Initial setup included creating a card and deck class, with matching test files. Moving forward we created a turn and round class, to hold and use the cards and deck. Finally we were required to edit the game and provided util class to get out 'game' working in the CLI, command line terminal. Part of the project requirements were to also make accompanying test files for each object class we created. This project focused on TDD, Test Driven Development, practices, and asked us to build out the tests before building out the code, so we had a deeper understanding of the process and benefits of TDD. 

## Class Requirements
#### Card Class
1. A Card represents a single flashcard
2. Each card has an id, a question, possible answers, and a correct answer
For example:
```
const card = new Card(1, 'What is Robbie\'s favorite animal', ['sea otter', 'pug', 'capybara'], 'sea otter');
```
#### Deck Class
1. Your Deck class should be initialized with an array of Card objects and should have an accompanying test file. It should know how many Cards are in the Deck.
For example:
```
const card1 = new Card(1, 'What is Robbie\'s favorite animal', ['sea otter', 'pug', 'capybara'], 'sea otter');
const card2 = new Card(14, 'What organ is Khalid missing?', ['spleen', 'appendix', 'gallbladder'], 'gallbladder');
const card3 = new Card(12, 'What is Travis\'s middle name?', ['Lex', 'William', 'Fitzgerald'], 'Fitzgerald');

const deck = new Deck([card1, card2, card3]);

deck.countCards(); // => 3
```
#### Turn Class
1. Instantiated with two arguments - a string (that represents a user’s guess to the question), and a Card object for the current card in play.
1. returnGuess: method that returns the guess
1. returnCard: method that returns the Card
1. evaluateGuess: method that returns a boolean indicating if the user’s guess matches the correct answer on the card
1. giveFeedback - method that returns either ‘incorrect!’ or ‘correct!’ based on whether the guess is correct or not.
For example:
```
const card = new Card(1, 'What is Robbie\'s favorite animal', ['sea otter', 'pug', 'capybara'], 'sea otter');
const turn = new Turn('pug', card);

turn.returnGuess();    // => 'pug'


turn.returnCard();     // => { id: 1,
                       //      question: 'What is Robbie\'s favorite animal',
                       //      answers: ['sea otter', 'pug', 'capybara'],
                       //      correctAnswer: 'sea otter'
                       //    }


turn.evaluateGuess();  // => false


turn.giveFeedback();   // => incorrect!
```
#### Round Class
1. returnCurrentCard: method that returns the current card being played
1. takeTurn: method that updates turns count, evaluates guesses, gives feedback, and stores ids of incorrect guesses
1. When a guess is made, a new Turn instance is created.
1. The turns count is updated, regardless of whether the guess is correct or incorrect
1. The next card becomes current card
1. Guess is evaluated/recorded. Incorrect guesses will be stored (via the id) in an array of incorrectGuesses
1. Feedback is returned regarding whether the guess is incorrect or correct
1. calculatePercentCorrect: method that calculates and returns the percentage of correct guesses
1. endRound: method that prints the following to the console: ‘** Round over! ** You answered <>% of the questions correctly!’
For example:
```
const card1 = new Card(1, 'What is Robbie\'s favorite animal', ['sea otter', 'pug', 'capybara'], 'sea otter');
const card2 = new Card(14, 'What organ is Khalid missing?', ['spleen', 'appendix', 'gallbladder'], 'gallbladder');
const card3 = new Card(12, 'What is Travis\'s favorite stress reliever?', ['listening to music', 'watching Netflix', 'playing with bubble wrap'], 'playing with bubble wrap');

const deck = new Deck([card1, card2, card3]);

const round = new Round(deck);

round.deck;   // => [card1, card2, card3];

round.returnCurrentCard(); // => { id: 1,
                           //      question: 'What is Robbie\'s favorite animal',
                           //      answers: ['sea otter', 'pug', 'capybara'],
                           //      correctAnswer: 'sea otter'
                           //    }

round.turns; // => 0

round.incorrectGuesses;     // => []

round.takeTurn('sea otter'); // => 'correct!'

round.takeTurn('spleen');   // => 'incorrect!'

round.turns; // => 2

round.incorrectGuesses;     // => [14]

round.currentCard();    // => { id: 12,
                        //      question: 'What is Travis\'s favorite stress reliever?',
                        //      answers: ['listening to music', 'watching Netflix', 'playing with bubble wrap'],
                        //      correctAnswer: 'playing with bubble wrap'
                        //    }

round.calculatePercentCorrect(); // => 50
```
#### Game Class
1. Should keep track of the currentRound
1. start: method that starts everything
1. Creates Cards
1. Puts Cards in a Deck
1. Creates a new Round using the Deck
1. invokes printMessage to display the message in the CLI
1. invokes printQuestion to kick off our helper functions that allow interaction via the CLI
```
game.currentRound; // => Round {...} (The new Round object that has been instatiated)
```

### JavaScript

**Create all of your feature code files in the `src` directory.**

We will be using the `module.exports` and `require` syntax to share code across files.

## How to View Your Code in Action

Once you are working through Iteration 3, you will want to start your server to test your functionality.
In the terminal, run:

```bash
node index.js
```

When the game is functioning appropriately, you will be prompted for each question, have the opportunity to select an answer, and will be given feedback. You will be able to play through the entire deck of cards:

![flash cards example gif](https://media.giphy.com/media/1zkb1q58eTiTH6D7wc/giphy.gif)

---

## Test Files Organization

Similar to feature code, your test code needs to be put in a specific place for it to run successfully.

**Put all of your test files in the `test` directory.** As a convention, all test filenames should end with `-test.js`. For instance: `Round-test.js`.

## Running Your Tests

Run your test suite using the command:

```bash
npm test
```

The test results will output to the terminal.

---

## Linting Your Code

Run the command in your terminal `npm run lint` to run the linter on your JavaScript code. There will be errors and warnings right from the start in this starter kit - the linter is still running successfully.

Your linter will look at the JavaScript files you have within the `src` directory and the `test` directory. 

---

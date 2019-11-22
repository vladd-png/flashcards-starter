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

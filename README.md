# Scope and Closure Challenge

The module challenge is the afternoon project or assignment that students work through independently. This expands on the guided project completed earlier with the instructor.


## (Josh) Written Questions:
1. In your own words, define closure (1-2 sentences).
  * A closure is when a variable in an inner scope references a variable or set of variables that live in their relative outer scope.
  * I personally think of scope as being analogous to a made-up extension to mathematical sets/sub-sets.
    * For example, if you have the sets S={{a,b,c}, x, y, z} and you let T={a,b,c}, then S={T,x,y,z}
      * In this analogy, the outser scope is the set S and the inner scope is the set T.
      * If you add the rule that anything in a subset is able to talk to all the elements in its superset
        then I think this is a good anology for closures.
      * Here is a mental image I make with this anology to scope and closures:

```
----------------------------------------------
|set-S:                                     |
|      |-------------|                      |
|      |set-T:       |                      |
|      |   a, b, c   |,     x,   y,   z     |
|      |             |                      |
|      |-------------|                      |
|--------------------------------------------
```

      * There is a wall-like container construct around the set-S and the same for set-T, sort of like scope.
      * In this made-up rule extention to set-theory, anything in a subset can talk to any elements in the superset
        but elements in the superset cannot talk to elements in the subset - they are aware there is a subset
        but what is inside the subset is made opaque to the elements in the superset.
      * To the elements x, y, and z in the superset they simply see another element named T,
        instead of seeing what is inside of T.
      * It is like the boundary around the sub-set T is a one-way mirror seeing outward, but not inward.  :)
      


2. Study the following code, then answer the questions below.

```js
function personalDice(name){
  return function(){
      // generate random number between 1 and 6
    const newRoll = Math.floor(Math.random() * 6);
    console.log(`${name} rolled a ${newRoll}`);
  }
}

const dansRoll = personalDice("Dan");

const zoesRoll = personalDice("Zoe");


dansRoll();
dansRoll();
```

a. Where is closure used in this code? How can you tell?
  * The closure is name.
  * The inside function has to look to its outer scope to find the variable.

b. Compare and contrast calling `dansRoll` the first and second time. What is always the same? What could change?
  * name is the same
  * newRoll changes

c. What is the lexical scope of `newRoll`? 
  * The variable newRoll sits at the scope of the Execution Context of the inner anonomous function.
  * The variable name sits at the scope of the Execution Context of the function personalDice.
  * The function personalDice sits at the global scope.

## (josh) Stetch:

1. Write a function that would allow you to do this using a closure. (This is another interview question we've seen before - when you're ready for answers, view an explanation here).

var addSix = createBase(6);

addSix(10); // returns 16

faddSix(21); // returns 27

```js
const createBase = (init) => {
    let base = init;
    return function(num) {
        // base is the closure
        // debugger;
        return base + num;
    };
};

var addSix = createBase(6);
const x1 = addSix(10); // returns 16
console.log(x1);
const x2 = addSix(21); // returns 27
console.log(x2);
```

2. Research the differences between functional programming and object oriented programming. Then, describe the pros and cons of functional programming vs object-oriented programming. This is a common interview question and great practice!
  * Functional programming is great.
  * OOP is trash and results in unnecessarily overly complicated codebases.

## JavaScript Foundations

## Scope and Closures

## Objectives

- Explain function scope
- Describe what closure is, how closure is created in a program and why it is important to understand closures in JavaScript  

## Introduction

This challenge focuses on both scope and closures.

In this challenge you will be working to build a `scoreboard` (in the console) that takes randomly generated data and keeps track of a game's progress. If you're not familiar with the rules of baseball what you need to know is this: there are 9 innings and teams take turns "at-bat." Teams can only score while they are at bat. A team stops being at bat once they have gotten 3 `outs` by either striking out or through game play. You can read more about baseball rules [here](https://www.rulesofsport.com/sports/baseball.html).

A scoreboard in a major league stadium looks something like this. In fact, the scoreboard at Fenway Park in Boston is actually quite famous. 

![Fenway Scoreboard](https://storage.googleapis.com/afs-prod/media/media:e959506330fd4e5890023c93cfbaac55/800.jpeg)

There are layers upon layers of nested functions within the game of baseball. Your challenge today will be to work through tasks associated with these layers, and ultimately to produce a scoreboard that logs in the console.

## Instructions

### Task 1 - Set Up Project and Tests

1. Fork the repo
2. Clone your forked version of the repo
3. cd into your repo and create a branch with your first and last name
4. open the terminal in your vs code and type `npm install`
5. next type `npm run test:watch` in your terminal
6. Complete your work making regular commits, once you have all your tests passing and you are ready to submit your work please see canvas for instructions on how to submit

### Task 2a - MVP code

Find the file `index.js` and complete the tasks.

### Task 2b - Written questions

Edit the `ReadMe` file with your answers.

1. In your own words, define closure (1-2 sentences).
2. Study the following code, then answer the questions below.

```js
function personalDice(name){
  return function(){
      // generate random number between 1 and 6
    const newRoll = Math.floor(Math.random() * 6);
    console.log(`${name} rolled a ${newRoll}`)
  }
}

const dansRoll = personalDice("Dan");

const zoesRoll = personalDice("Zoe");


dansRoll();
dansRoll();
```

a. Where is closure used in this code? How can you tell?
b. Compare and contrast calling `dansRoll` the first and second time. What is always the same? What could change?
c. What is the lexical scope of `newRoll`? 


### Task 3 - Stretch Goals

After you have completed the requirements, **create** a new file called `stretch.js` and practice more with closures. There are no tests for these problems.

See if you can complete one or more of the following challenges:

1. Write a function that would allow you to do this using a closure. (This is another interview question we've seen before - when you're ready for answers, view an explanation [here](https://www.coderbyte.com/algorithm/3-common-javascript-closure-questions)).

```js
var addSix = createBase(6);
addSix(10); // returns 16
addSix(21); // returns 27
```

2. Research the differences between functional programming and object oriented programming. Then, describe the pros and cons of functional programming vs object-oriented programming. This is a common interview question and great practice!

## Resources

📚 [Scope and Closures Guide](https://css-tricks.com/javascript-scope-closures/)

🧠 ["I never Understood Closures" Blog](https://medium.com/dailyjs/i-never-understood-javascript-closures-9663703368e8)

## Submission Format

Please see Canvas for cohort specific submission instructions 

npm run test:watch
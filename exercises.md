## Exercises for Week 1

For each code snippet, reason about what output you would expect to see in the console.  First, how many statements should you see in the console?   What assignments are occurring, if any? Then, what exactly should those logs say?   Reason through what you expect to see before you run the code.

Be careful to clear the ```<script>``` section of your HTML document before running each snippet, otherwise you could contaminate your variable assignments or just generally make the code more confusion to reason about.
Snippet 1:
```
console.log("Hi Mom!");
console.log("Welcome to Intro to JavaScript!");
```

Snippet 2:
```
console.log("Hi Mom!", "Welcome to Intro to JavaScript!")
```

Snippet 3:
```
var myVariable = 100;
myVariable + 10;
console.log(myVariable);
```

Snippet 4:
```
var anotherVariable = 100;
anotherVariable = anotherVariable + 200;
console.log(myVariable);
```

Snippet 5:
```
console.log(something);
var something = "abcdefg";
console.log(something);
```

Snippet 6:
```
var willRainToday = true;
console.log("It will rain today: ", willRainToday);
willRainToday = false;
console.log("It will rain today:" willRainToday);
```

Snippet 7:
```
var test = 1000;
test = test + 1000;
test + 100;
console.log(test);
```

Snippet 8:
```
var tricky = 500;
tricky = tricky + 5000;
var sneaky = 1600;
console.log(sneaky > tricky);
```

Here's an object in JavaScript. Copy it into your HTML document's script section.

```
var chessPlayer = {
  "computerPlayer": true,
  "numberOfMoves": 3,
  "score": 500,
  "hasKing": true,
  "hasBishop": true,
  "hasAllPawns": false,
  "wonGame": false,
}
```
How would you extract the following data and send it to the console?
1) Get the number of moves in the game so far
2) Get this player's score
3) Log out whether this player has its bishop, and log it next to a string describing what you're logging

How could you update the score?  You should log the chessPlayer object before and after making the update/mutation.  

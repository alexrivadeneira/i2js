Welcome to Class!

⭐⭐⭐ Thanks for coming to class this week - [click here to see the homework exercises.](exercises.md)⭐⭐⭐
## Part 1 Outline

### As you come in:

* Navigate to [nerdyperson.com](http://www.nerdyperson.com) (This webpage) 🤓
* Download [Sublime Text Editor](https://www.sublimetext.com)
* Download [Google Chrome](https://www.google.com/chrome/)

### Class goals
* Transition from web consumer to producer/maker/creator
* Create an interactive web application from scratch using JavaScript (demo)

### Guidelines
* Pay attention to the right things - please be alert when I'm talking.  It's difficult to put aside your code, but I'm trying to point out information that might be helpful when you're working independently.
* We'll alternate between lecture with the group and time to work individually.
* We all work at different paces and have different experience.
* There are additional volunteers to help out if you're getting stuck, but please remember, there are only 1-3 instructors and many students!


### JavaScript
JavaScript is a programming language that, along with CSS and HTML, allows us to build interactive web pages.

Here are the main categories or **types** of things that we'll be interacting with in JavaScript.

Picture JavaScript as a vast ocean.  There are a number of different fish swimming around in this ocean.  In reality, this is a bit more complicated, but for our purposes, these are the fish in our sea:

* Strings - strings are text or characters, including numbers, and spaces, wrapped with single or double quotation marks
```
"Welcome to class"
"Goodnight Moon"
" "
'Berkeley '
' Berkeley '
"A"
'b'
'12345'
"12345"
```
* Numbers
```
4
-50
100
5.522
```
* Boolean - true or false
```
true
false
```
* Document Objects - HTML components of a web page. Essentially any piece of a webpage that we want to target for some sort of interaction or modification.  If you've worked with HTML before, these might look familiar.
```
<h1>My Header</h1>
<div id="redBox"></div>
<a href="#">Link to Nowhere</a>
```


### Open Dev Tools JavaScript Console
Here's the keyboard shortcut for opening the Chrome Developer Tools / Console: ```Control + Shift + J``` on PC on ```Command + Option + J``` on Mac.

To get a taste of how powerful the JavaScript console is, navigate to any site and try typing in this, then press the return key:

```
document.body.style.backgroundColor = "black";
```
⚠️ Note, don't add any extra capitalization - be careful to copy the code almost exactly.

or if you really want to go crazy...

```
setInterval(function(){
  var colors = ["red", "yellow", "black", "green", "blue"];
  document.body.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
  }, 1000);
```

🙀 We can totally transform web pages using JavaScript.

### Transforming values and making comparisons
**Exercise**: Open the JavaScript console in Chrome. Try the following actions (remember to hit the return key after you input an expression)
1. Adding, subtracting numbers
2. Adding strings together
3. Comparing numbers using ```>``` or ```<```
4. Testing for equality using the **strict comparison operator** ```===```

Try typing in the following lines and see what happens:
```
1 + 100;
"Berkeley";
"Berkeley" + 100;
1 === 1;
1 === 2;
"Berkeley" === "El Cerrito";
5 > 3;
10000 < 1;
" " === " ";
true === false;
true === true;
document.body === document.body;
```

🤔 **Exercise**: What are the **type(s)** in each line above?

## HTML document
All web pages have a document structure.
Copy and paste the following into Sublime (or, after saving your file as a .html file, try typing ```<h``` and then the tab key!)

```
<!DOCTYPE html>
<html>
<head>
	<title></title>
</head>
<body>

</body>
</html>
```

Review! Almost all HTML tags have opening and closing parts.
Try adding a few elements to your page inside the ```<body>``` section, ie, between ```<body>``` and ```</body>```:

```
<h1>You could add a header</h1>
<h2>You could add a smaller header</h2>
<p>Or some paragraph text. Or some paragraph text. Or some paragraph text. Or some paragraph text. Or some paragraph text.</p>
<strong>Try making text bold</strong>
```

Don't forget to give your page a title as well in the ```<title>``` section.

To add JavaScript to our document, we need to add the ```<script>``` section ***at the bottom of, and nested inside the ```<body>``` section:***


```
<!DOCTYPE html>
<html>
<head>
	<title>Experimenting with JavaScript</title>
</head>
<body>

  <script>

  </script>
</body>
</html>
```

## console.log()
In order to save the JavaScript we're writing, we'll add it to our HTML document.   We still want to send output to the JavaScript console, however, so we'll need to use a built in function called ```console.log()```.

```console.log()``` is a built in function in JavaScript.  For our purposes, it lets us send things to the console in Chrome Developer tools.  It's mostly used for debugging purposes.

Let's send something to the console!  Remember, this goes insides the ```<script></script>``` section of your HTML document:

```
console.log("hi Mom!");
```
Open your web page in Chrome and open the Developer tools to see if you successfully sent your message to the console.

Review: What is the type of the thing we just sent to the console?

Add some more console.log statements to your HTML document:
```
console.log(1 + 2);
console.log("hello" + " " + "world");
console.log(true);
console.log(2 === 2);
console.log(true === false);
```

We can comma separate entries we are sending to the console:

```
console.log(1, 2, 3);
console.log("Berkeley", 1980);
console.log(true, true, false, false);
console.log(2 === 2, 3 + 5, true === false);
```

## Assigning variables

Let's use the ```var``` keyword to assign data to variables.  Variables help us carve out a piece of computer memory to store data so we can use it again later.

```
var score = 100;

```

We declare the data variable, and then can reuse that variable throughout our program/script:

```
var score = 100;

console.log(score);
console.log(score - 5);
console.log(score + 100);

```
Notice that the variable ***score*** itself isn't mutated unless we reassign it:

```
var score = 100;

console.log(score);
console.log(score - 5);
console.log(score);

```

**Exercise**: Without a computer, reason about what you would expect to see in the console when you run the following code snippets in isolation. THEN check your logic by actually executing the code.

```
var someNum = 200;
console.log(someNum);

```

```
var stringVariable = "Berkeley";
console.log(stringVariable);

```

```
var myName = "Alex";
myName = "C3PO";
myName = "Charlie";
console.log(myName);
```

Trickier:

```
var yourName = "Bryce";
var myId = 12345;
myId = 600;

```

```
var moreData = 600;
console.log(moreData);
console.log(moreData + 1);
console.log(moreData);

```


```
var newScore = 600;
console.log(newScore);
moreData = newScore + 1;
console.log(newScore);

```

```
var state = true;
state = false;
console.log(state);
```

Thinking about equivalencies/comparisons:

```
console.log(1 > 2);
```


```
console.log("Alex" === "Alex");
```

```
console.log(' ' === '     ');
```

Think about equivalencies/comparisons and variables:
```
var highScore = 900;
var playerScore = 1000;
console.log(highScore > playerScore);
```

```
var highScore = 900;
var playerScore = 1000;
console.log("Is high score unbeaten?", highScore > playerScore);
```

```
var memberId = 12345;
var lookupId = 12345;
console.log("Ids match?", memberId === lookupId);
```

```
var firstName = "Bob";
var lastName = "Barker";
var fullName = firstName + " " + lastName;
console.log(fullName === "Bob Barker");
```

```
var someNum = 1;
someNum = 3;
var anotherNum = 3;
console.log(someNum === anotherNum);
```


```
var someNum = 20;
someNum = 30;
var anotherNum = 30;
anotherNum = someNum + anotherNum;
console.log(anotherNum > someNum);
```




## Objects
One final type of thing we'll explore in JavaScript is an object (similar to Document Object we already saw):

In this case, I've created a ```bankAccount``` object to store data about a user's bank account.

```
var bankAccount = {
  "userName": "Alex",
  "accountID": 91291,
  balance: 10,
};
```

Objects are collections of key-value pairs.  The keys are strings, and the values can be strings, numbers, booleans, other objects, and more.


If I want to access the user name on this bank account object, I can use the variable name and then the key name to get access to the data inside:

```
bankAccount["userName"];
```

**exercises**
1. Try logging the other data from the bankAccount object to the console.
2. Build your own bankAccount object.
3. See if you can figure out how to add and subtract money from your bank account object.
4. Create a playerObject for a character in a hypothetical computer game.  Give your character properties including name, hair color, avatar color, score, currency, whether the character can talk (boolean).
5. What other data might you store in an object?





### Further Exploration
* ["Fixed mindset" vs "Growth mindset" video and discussion, Carol Dweck](https://www.ted.com/talks/carol_dweck_the_power_of_believing_that_you_can_improve)
 * View source code on some of your favorite webpages
 * [FreeCodeCamp exercises](https://www.freecodecamp.org): Basic HTML and HTML5, Basic CSS
* [W3Schools exercises](https://www.w3schools.com/html/exercise.asp?filename=exercise_attributes1)

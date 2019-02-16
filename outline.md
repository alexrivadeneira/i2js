Welcome to Class!

## Part 1 Outline

### As you come in:

* Navigate to [nerdyperson.com](http://www.nerdyperson.com) (This webpage)
* Download [Sublime Text Editor](https://www.sublimetext.com)
* Download [Google Chrome](https://www.google.com/chrome/)

### Class goals
* Transition from web consumer to producer/maker/creator
* Create an interactive web application from scratch using JavaScript (demo)

### Guidelines
* Pay attention to the right things - please be alert when I'm talking.  It's difficult to put aside your code, but I'm trying to point out what I think are important concepts.
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
* Document Objects - HTML components of a web page. Essentially any piece of a webpage that we want to target for some sort of interaction or modification.
```
<h1>My Header</h1>
<div id="redBox"></div>
<a href="#">Link to Nowhere</a>
```


### Open Dev Tools JavaScript Console
Here's the keyboard shortcut for opening the Chrome Developer Tools / Console: Control + Shift + J on PC on Command + Option + J on Mac.

To get a taste of how powerful the JavaScript console is, navigate to any site and try typing in this:

```
document.body.style.backgroundColor = "black";
```

or if you really want to go crazy...

```
setInterval(function(){
  let colors = ["red", "yellow", "black", "green", "blue"];
  document.body.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
  }, 1000);
```

We can totally transform web pages using JavaScript.

### Transforming values and making comparisons
Try the following in the console:
Adding, subtracting numbers
Adding strings together
Comparing numbers using ```>``` or ```<```
Testing for equality using the strict comparison operator ```===```

What happens when you type the following lines into the console and hit the return key?
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

🤔 **Exercise**: From the list above, which **types** are we interacting with in each of the lines we just inputted into the console?

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

We need to add the ```<script>``` section at the bottom of, but nested inside the ```<body>``` section:


```
<!DOCTYPE html>
<html>
<head>
	<title></title>
</head>
<body>

  <script>

  </script>
</body>
</html>
```

Review! Almost all HTML tags have opening and closing parts.

## console.log()
In order to keep working with JavaScript in our actual HTML document, we're going to use a JavaScript built in function called ```console.log()```. We use ```console.log()``` when we want to send expressions to be evaluated from our webpage.

```console.log()``` is a built in function in JavaScript.  For our purposes, it lets us send things to the console in Chrome Developer tools.  It's mostly used for debugging purposes.

Let's send something to the console!  Remember, this goes insides the ```<script></script>``` section of your HTML document:
```
console.log("hi mom!");
```
Review: What type of thing did we send?

```
console.log(1 + 2);
console.log("hello" + " " + "world");
console.log(true);
console.log(2 === 2);
console.log(true === false);
```

We can comma separate out entries we are sending to the console:

```
console.log(1, 2, 3);
console.log("Berkeley", 1980);
console.log(true, true, false, false);
console.log(2 === 2, 3 + 5, true === false);
```

## Assigning variables

Let's use the ```var``` keyword to assign data to variables.  Variables help us carve out a piece of computer memory to store data.

```
var data = 100;

```

We declare the data variable, and then can reuse that variable throughout our program/script:

```
var data = 100;

console.log(data);
console.log(data - 5);
console.log(data + 100);

```
Notice that data itself isn't mutated unless we reassign it:

```
var data = 100;

console.log(data);
console.log(data - 5);
console.log(data);

```

Without a computer, reason about what you would expect the final console statement to be, THEN check your logic by running:

```
var someNum = 200;
console.log(someNum);

```

```
var stringVariable = "Berkeley";
console.log(stringVariable);

```

```
var moreData = 600;
console.log(moreData);
moreData + 1;
console.log(moreData);

```


```
var moreData = 600;
console.log(moreData);
moreData = moreData + 1;
console.log(moreData);

```

```
var state = true;
console.log(state === false);
state = false;
console.log(state);
```

## Objects
One final type of thing we'll explore in JavaScript is an object:

```
var bankAccount = {
  "name": "Alex",
  "accountID": 91291,
  balance: 10,
};
```

### Further Exploration
* ["Fixed mindset" vs "Growth mindset" video and discussion, Carol Dweck](https://www.ted.com/talks/carol_dweck_the_power_of_believing_that_you_can_improve)
 * View source code on some of your favorite webpages
 * [FreeCodeCamp exercises](https://www.freecodecamp.org): Basic HTML and HTML5, Basic CSS
* [W3Schools exercises](https://www.w3schools.com/html/exercise.asp?filename=exercise_attributes1)

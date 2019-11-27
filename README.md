
# p5js Tutorial for Codeninja

# Introduction
## What is p5js
## The p5js Editor
Click here to open the p5js editor
[https://editor.p5js.org](https://editor.p5js.org/)

This is where we will be writing all of our code. When you open it, look for these things.
- At the top are the **Play and Pause Buttons.** Press these to run or stop your code at any time.
- On the left is the **Code Window.** This is where you time your code!
- On the right is the **Preview Window.** This is where you can see what you draw with your code. Press the Play button now, and you should see a boring gray square (We'll change that soon, don't worry!)
- On the bottom is the **Console.** Here you can *log* text from your code. Every programming language in the world uses a console somehow. We'll be using it for a little while to learn the basics, then we'll learn how to draw with p5.

# The Console
When you first open the editor, your code should look like this:
```javascript
function setup() {
  createCanvas(400, 400);
}

function draw() {
  background(220);
}
```
Delete all of it! We're going to start from scratch.
## Hello, World
It's an old programmer tradition to make your first program say *Hello, world*. That's what we're going to do. 

You've already deleted all the code in the code editor, so enter this there now. Make sure you write it exactly like this.
```javascript
console.log('Hello, world!');
```
Then, press the play button. What happens?

The console should look like this:
```
Hello, world!
```
Great job, you've done your first program.
A computer program is made out of commands. `console.log` is a command that *logs* some text to the *console*.

In Javascript, every command ends with a *semicolon* **`;`**. You should only put one command on a line. Don't worry if you forget a semicolon; Javascript is forgiving, but other languages aren't! This is one reason why Javascript is good for beginners.

Let's add more commands now.
```javascript
console.log('Hello, world!');
console.log('I like learning how to program.');
console.log('My favorite animal is a cat.');
```
The output of this program will be:
```
Hello, world!
I like learning how to program.
My favorite animal is a cat.
```
> ### Extra Challenge
> Your favorite animal might not be a cat. You should reconsider, but if not, take this challenge:
> - Edit your code to make it say a different animal.
> - Write a fourth command that says anything you want.
> - Write as many commands as you want to.

## Comments

Comments are simple: anything after `//` on a line will be ignored by the computer. Comments are only for humans to read, and you should use them to describe your code.

```javascript
// This is as comment. it doesn't do anything!
console.log('Hello, world!'); // this is a comment, too.
// this is a third comment.
```

## Variables
Making the computer say things in the console is cool, but we can do that with Microsoft Word. We want the computer to do things *for* us. Like math. Or remembering stuff. This is where we use *variables.* If you have taken algebra in school, you have already used them!

A variable *stores* a piece of data to use later. Put this example into your code editor:

```javascript
let hiWorld = 'Hello, world';
console.log(hiWorld);
```
The first command creates a variable named `hiWorld`, and makes it equal `"Hello, world!`

### Strings

There are different *types* of variables that store different kinds of information. `'Hello, world!'` is a *string*. Strings are for text, words, sentences, and letters.  A string **always** has two *quotation marks* `'` at the start and at the end.

You can tell when something is a string, because the code editor will turn it a light green.

Having *mismatched quotation marks* will cause errors!
You can add two strings together by using the `+` symbol.
```javascript
let hiWorld = 'Hello' + 'world';
console.log(hiWorld);
```
```
Helloworld
```
Helloworld???  When you add two strings together, it does *not* put a space between them. You have to do that yourself.
```javascript
let hiWorld = 'Hello ' + 'world';
console.log(hiWorld);
```
```
Hello world
```

### Numbers

Another kind of variable is a *number*. Write these commands in your code editor.
```javascript
let x = 10 + 3;
console.log(x);
```
Look at what the output is. Instead of `10 + 3`, it should log:
```
13
```
Unlike strings, numbers will automatically do math together.
## Functions
Believe it or not, programmers are ***lazy.*** We don't like doing things over and over and over again - we have computers to do that! When you starting thinking about how to make the computer do repetitive tasks, or *automate* them, that's when you've started to **think like a programmer.**

Let's say you want a program that prints this:
```
there was a farmer who had a dog, and
BINGO
was his name-o
BINGO
BINGO
BINGO
was his name-o
```
You might write this:
```javascript
console.log("there was a farmer who had a dog, and");
console.log("BINGO");
console.log("was his name-o");
console.log("BINGO");
console.log("BINGO");
console.log("BINGO");
console.log("was his name-o!");
```
Let's break this down:
- You have to type `console.log` seven times.
- You have to type `console.log("BINGO");` four times.
- If you want to change the name of the dog from `BINGO` to something else, you have to re-type it... five _more_ times.

This is starting to sound more like writing lines on a chalkboard. So let's use **function** to speed things up.
```javascript
function sayDogName() {
	console.log("BINGO");
}
console.log("there was a farmer who had a dog, and");
sayDogName();
console.log("was his name-o");
sayDogName();
sayDogName();
sayDogName();
console.log("was his name-o!");
```
The output is the same as above! You've created a _function_. A function is a _code_ block with a name. Your function is named `sayDogName`. Any time you _call_ a function with `sayDogName();`, it runs everything inside it.
Functions make it easier to change your code later. Change the name of the dog like this:
```javascript
function sayDogName() {
	console.log("FIDO");
}
```
Now when you run your code:
```
there was a farmer who had a dog, and
FIDO
was his name-o
(3) FIDO
was his name-o
```
You only had to change one string!

> In the p5 editor, multiple `console.log`s that are the same don't print, and just add a number to the first one. That's why it says `(3) FIDO` instead of printing `FIDO`  three times in a row.

Functions are the best tool javascript has to keep from re-writing or copy-pasting many, many lines of code. Any time you're facing a problem that requires rewriting the same thing over and over again, always try to do it with a function instead.

We'll learn about _loops_, another way to do repetitive things, in a later section.
# Drawing with p5

`console.log` is boring and lame. Making games is fun. To make games you have to draw things on the screen. This is where p5 comes in!

## `draw()` and `setup()`

go to **File -> New** in the menu bar to make a new sketch. Remember the starter code we deleted earlier? We're going to use that now.
```javascript
function setup() {
  createCanvas(400, 400);
}

function draw() {
  background(220);
}
```
Now that you know what functions are, this code might make more sense.

The `setup()` function runs one time. when you press the play button.

After `setup()` has run, `draw()` runs over and over again, _sixty times every second._ That's way, way faster than a human can draw, but computers do it just fine.

Change your code to this:

```javascript
function setup() {
	createCanvas(400, 400);
}

function draw() {
	circle(mouseX, mouseY, 30);
}
```

Click play, then wiggle your mouse around on the canvas. You can paint a picture using circles!

What this code does:
- `setup()`: create the canvas. It's 400 pixels by 400 pixels.
- `draw()`: _sixty times each second_, do this:
	- Draw a new circle where the mouse is. The circle has a radius of 30 pixels.

The result? _A whole lot of circles._

Let's make it so instead of painting a long line of circles, it just paints one circle underneath the mouse. Change your code to this:

```javascript
function setup() {
	createCanvas(400, 400);
}

function draw() {
	background("gray");
	circle(mouseX, mouseY, 30);
}
```

With the extra line `background("gray");`, now the `draw()` function does this:
- draw gray over the whole canvas, _on top_ of whatever was there before.
- draw a circle where the mouse is.

Now, instead of a line of circles that never goes away, it looks like there's just one circle following your mouse around.

<!-- TODO -->

## The p5 Reference

What if you want to do more than just draw a circle? Instead of just telling you how to do it, I'm going to teach you how to learn that yourself.

The [p5js reference](https://p5js.org/reference/) contains _every_ function and variable that p5 has. You can use any of them.

This might be a little bit scary, because there's a lot of functions. But being able to read a reference for a _code library_ (p5.js is a _library_) is one of the best skills a programmer can have.

Let's learn how to change our circle from white to **green**. And get rid of the black outline, while we're at it.

Search "fill" in the search box at the top of the reference. Click on the result that says "***fill** method in **p5***". A bunch of examples should appear that look like this:

> ```javascript
> // Grayscale integer value
> fill(51);
> rect(20, 20, 60, 60);
> ```

> ```javascript
> // Named SVG/CSS color string
> fill('red');
> rect(20, 20, 60, 60);
> ```

Huh, this looks useful. If you put `fill()`, it changes the fill color of the things that come after. Let's change our code to use `fill()`.

```javascript
function setup() {
	createCanvas(400, 400);
}

function draw() {
	background("gray");
	fill("green");
	circle(mouseX, mouseY, 30);
}
```
Simple!

Now, let's change the outline. p5 calls the outline of something the _stroke_. Search for the `stroke()` method and look at the examples.

> ```javascript
> // Named SVG/CSS color string
> stroke('red');
> strokeWeight(4);
> rect(20, 20, 60, 60);
> ```

This looks useful, but none of these examples do what we want: get _rid_ of the stroke. Search 'stroke' again, and you'll see different function called `noStroke()`. This example looks way better.

> ```javascript
> noStroke();
> rect(20, 20, 60, 60);
> ```

So let's change our `draw()` method to use `noStroke()`.

```javascript
background("gray");
fill("green");
noStroke();
circle(mouseX, mouseY, 30);
```

Good job!

> ### Extra Challenge
> Use the p5 reference to learn how to draw a square instead of a circle, then do it in your code.

## Drawing with Variables
## Drawing with Functions
# Flow
## If
## While
## For
# More Variables
## Booleans and Boolean Operators.
## Arrays
## Objects
# Advanced
## Nesting
## Advanced Functions
### Arguments
### Return
### Functions *are* Variables
<!--stackedit_data:
eyJoaXN0b3J5IjpbNDM2ODU1OTkxXX0=
-->
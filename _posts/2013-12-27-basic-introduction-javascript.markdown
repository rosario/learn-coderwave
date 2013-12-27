---
layout: post
title:  "Basic Introduction to Javascript"
date:   2013-12-27 13:34:05
categories: javascript
---

Javascript is one of the most popular programming languages, supported by all modern desktop, tablet and mobile browsers. Here's a short introduction.


## Do you need to learn Javascript?

Short answer: **Yes, you do**. Javascript is important because is the language used by all modern web browsers. Basically, Javascript is one of the most popular programming languages in the world.

Also, the Web has become an important platform for applications and interactive data visualizations. Learning how to code in Javascript could open up interesting possibilities. 


## How to write Javascript

Javascript runs inside your browser (although projects like [node.js](http://nodejs.org/) make it possible to write javascript also for server programming). First of all, we need to create a simple HTML page:

Open up a Text Editor ([Sublime Text](http://www.sublimetext.com/) is a good one) and **create a new  file** and save it as as _page.html_. The content of _page.html_ should be: 

{% highlight html %}
    
    <!-- This is the content of page.html -->
    <html>
    <head>
      <script type="text/javascript" src="example.js"></script>
    </head>
    <body><p> Example page</p></body>
    </html>
{% endhighlight %}

Inside the same folder, **create another file**, and save it as _example.js_. The content of the first Javascript program should be:
    
{% highlight javascript %}
// This is the content of example.js
console.log('hello');
{% endhighlight %}

At this point, you should have two files, the HTML and the Javascript file. We need to test that everything is setup correctly. Open up your browser (_Chrome_ is recommended) and load your _page.html_. 

> Note: You just need to double click on the _page.html_ file to load it.

If you're using Chrome, **right click** on the page, and select _Inspect Element_. You should see a bottom panel. Click on _Console_. If everything went as expect, you would be able to see the message "hello".

<div class='center'><img src="{{ site.baseurl }}/images/javascript-hell-world.png" /></div>

## What's happening?

The HTML page (called _page.html_) is loaded by your browser. The line starting with __script__ is telling your browser to load the file (called _example.js_). The browser then load the program and runs it. The instruction **console.log** is showing the message _'hello'_.

Congratulations, that's your first Javascript program!

> Note: Every time you change and save the file _example.js_, you **have** to reload the _page.html_ with your browser if you want to see any changes!

## How to use this tutorial

The best way to learn how to code is by typing your own programs! Don't copy/paste from here. 
Instead, read and understand the examples, then change the _example.js_ file and reload the browser to see what changes.

You might find some error. **Don't Panic - Use Google**. It might be the case few thousands people  have already found a solution, learn how to use _Google_ to _debug_ your program.


## Javascript Syntax

Javascript has its own syntactic rules, and we need to learn those if we want to write correct programs. 

### Statements

Javascript programs are made of statements. Statements are executed from top to bottom.

In Javascript there are:

* **variables definition** statements (_var_)
* **conditional** statements (_if_ and _switch_)
* **looping** statements (_while_, _for_, and _do_) 
* and **breaking** statements (_break_, _return_). 

A _block_ in Javascript is a sequence of statements wrapped in curly brackets { ...  }.

### Whitespaces and Semicolons
It is _important_ to separate keywords with a space. For example, this is correct:

{% highlight javascript %}
var hello = "hi there";
{% endhighlight %}

Instead, if we forget to add the space:

{% highlight javascript %}
varhello = "hi there";
{% endhighlight %}

That's not ok, because Javascript does not recognise the keyword _varhello_.

Semicolons are used to terminate _statements_ like in the examples above (note: it's actually more complex than that, but at this stage it should be enough to know that semicolons are important to separate between statements).

### Variables

In the previous example, we've seen the keyword **var**. That's used to define _variables_. You might aks, **what's a variable**? 

_Variables_ are names used as placeholders. We store data in _variables_. Let's see few examples. If we want to store the sum of two numbers:

{% highlight javascript%}
var sum = 123 + 2;
{% endhighlight %}

If we want to store the address of a restaurant: 

{% highlight javascript%}
var address = "123 King Street, London";
{% endhighlight %}

In the previous examples, we are _defining_ two variables, _sum_ and _address_, and we use them as placeholders to contain respectively the sum and the address data.

> Variables are called _variables_ because during the program execution, their value could potentially change. The sum could increase or decrease, and the address of the restaurant might change. 


### Javascript Types

In Javascript, we can write **Numbers**, for example: 1, 1234, or 3.14.  Negative numbers are formed by using a dash prefix, like in -123, or -20.23.

We've also seen **Strings**, for example "hello", or "123 King Street, London". Strings are sequence of characters, wrapped inside a double quote or a single quote (like in 'this example').

Javascript also support **Booleans**. A boolean type can be either _true_ or _false_. For example:

{%highlight javascript%}
var is_christmas_now = false;
{% endhighlight %}



## If statement in Javascript

The _if_ statement alter how a program is executed, depending of the value of the _expression_. 

{% highlight javascript %}
if (expression){
  // if the expression is true
  // the program execute this branch
}
else{
  // otherwise, the program execute this one
}
{% endhighlight%}


To better understand how it works, let's see what happens in this example. When the expression is *true*:

{% highlight javascript %}

var is_christmas_now = true;
if (is_christmas_now) { 
  console.log('Merry Christmas!');
}
else {
  console.log('Not Today!');
}
{% endhighlight %}

Let's rewrite again the same program, but this time set the variable to _false_:

{% highlight javascript %}

var is_christmas_now = false;
if (is_christmas_now) { 
  console.log('Merry Christmas!');
}
else {
  console.log('Not Today!');
}
{% endhighlight %}



### Switch statement 

Similar to the _if_ statement, the _switch_ statements can handle more conditions. For example:


{% highlight javascript %}
var fruit = "Oranges";

switch (fruit) {
  case "Oranges": 
    console.log('I like Oranges');
    break;
  case "Apples":
    console.log('I like Apples');
    break;
  case "Cherries":
    console.log('I like Cherries');
    break;
  default: 
    console.log("I don't think I like that");
}
{% endhighlight %}

Again, it would be better to test the same program with different values for the _fruit_ variable.

### Loops: While and Do statements


In a programming language, you often hear the word **loops**. We talk about loops when there are a certain set of statement (or computer instructions) that need to be repeated for a certain number of times. For example, you need to use a _loop_ when you want to display the content of a list of data. Generally speaking, you might need to use a loop every time you need to perform calculation on a set of data.

Javascript has three statements for looping through data: **while**, **do** and **for**.

### While Statement

The _while_ loop executes the statements as long as the expression is valid (or true). When the expression become _false_, the loop ends. Note, if the expression is not valid, the block is not executed at all. Example:

{% highlight javascript %}
var counter = 0; 
while (counter < 10){ 
  console.log("This message will be printed 10 times");
  counter = counter + 1;
}
{% endhighlight %}

Another example, the following loop is not executed because the expression is not true. 


{% highlight javascript %}
var counter = 100; 
while (counter < 10){
  console.log("Is this message shown?")
  counter = counter + 1;
}
{% endhighlight %}


### Do Statement

Very similar to the _while_ statements, but this time the code block is executed before, and the expression is checked at the end. Compare this code: 


{% highlight javascript %}
var counter = 0; 
do {
  console.log("This message is printed 10 times");
  counter = counter + 1;
} while (counter < 10);
{% endhighlight %}

You will see the message is actually printed 10 times. If we change to initial value of the variables: 


{% highlight javascript %}
var counter = 100; 
do {
  console.log("This message is printed 10 times");
  counter = counter + 1;
} while (counter < 10);
{% endhighlight %}

Now, you'll see how the message is printed once. That's because the expression _counter < 10_ is only checked after the block of code is executed.

### For loop Statement

The _for_ statement is another form of  Javascript _loop_. It has a specific syntax: 


{% highlight javascript %}
var counter;
for(counter = 1; counter <=10 ; counter = counter + 1){ 
  console.log('This message is printed ' + counter + ' times');
}
{% endhighlight %}


## Functions and Return statements

A function specify a sequence or block of statements. Typically you want to pass some _parameters_ to the function. For example: 


{% highlight javascript %}
function sum(a, b) { 
  var total; 
  total = a + b;
  return total;
}
{% endhighlight %}

In this example, we are defining a _function_ called **sum**. We are _passing_ two parameters (_a_ and _b_). When you want to return a value from a function, you can use the _return_ statement.

## Objects

We've already seen few basic data types. Numbers (12, 123 for example), Strings ("Hi there", "John Smith" for example), Booleans (true and false).

The **Object** is an important data type too. We use _objects_ as containers to group _basic_ data types. For example, we might want to create an object to store the details of a _User_; 


{% highlight javascript %}
var user = {
  name: 'Thomas A. Anderson',
  nickname: 'Neo',
  gender: 'Male',
  height: '1.85'
}
{% endhighlight %}

Also, we might want to create an object to store the details of a venue:


{% highlight javascript %}
var venue = { 
  name: 'Casa Mia',
  cuisine: 'Italian',
  address: '209 King St, London',
  post_code: 'W69JT',
  ratings: {
    clean: 10,
    food: 10
  }
}
{% endhighlight %}


> Note: we can also insert an object inside another object (see the _rating_ object?).

### Read and Update the Object data

After the object has been initialised, we can now access its data using the following notation: 

{% highlight javascript %}
var name = venue.name;
var food_rating = venue.ratings.food;
{% endhighlight %}

We can easily update the objects attributes:


{% highlight javascript %}
venue.name = 'Casa Italia';
{% endhighlight %}

We can also add **more attributes** in the same way: 

{% highlight javascript %}
venue.telephone = '0123456789';
{% endhighlight %}


## Arrays 

Arrays are used to store a sequence of objects or basis types (such as Numbers and String). Let's see few examples: 

{% highlight javascript %}
var names = ['Trinity','Neo','Agent Smith','Morpheus'];
{% endhighlight %}

We could also define an array to store a sequence of numbers: 
  
{% highlight javascript %}
var ratings =[1,2,3,4,5,6];
{% endhighlight %}

The first element of the array _always_ starts at zero. If we want to get the first element, we need to use the square brackets notation:
    
{% highlight javascript %}
var first = names[0]
{% endhighlight %}

This will return the string 'Trinity'. If we want to access the second element: 


{% highlight javascript %}
var second = names[1]
{% endhighlight %}


Javascript **arrays** have a length method, for example:

{% highlight javascript %}
names.length
ratings.length
{% endhighlight %}


We can use the _length_ inside a **for loop** example:


{% highlight javascript %}
var position;
for(position = 0; position < names.length; position = position + 1){
  console.log(names[position]);
}
{% endhighlight %}

# Conclusions

Javascript is a powerful programming language. It is used by all modern browsers, including mobile and tablets devices. It might seem a bit scary in the beginning, but it's not so hard after a while, and a bit of patience.

## What's next?

That's just a short introduction, and there's much more to cover. If you're interested in learning more there are some great online resources:

* [Javascript for Cats](http://jsforcats.com/)
* [Lots of free ebooks](http://jsbooks.revolunet.com/)
* Some free courses on [CodeSchool](https://www.codeschool.com/paths/javascript)
* [Codecademy on Javascript](http://www.codecademy.com/tracks/javascript)

## Or, if you're tired of online tutorials...

If you're getting tired of online tutorials, and you're based in London, you might also want to [learn Javascript with Coderwave](http://coderwave.com/courses/javascript-jquery-workshop) in a workshop ;)



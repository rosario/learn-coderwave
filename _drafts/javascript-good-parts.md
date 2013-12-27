# Why Javascript

_Javascript_ is important because it's the programming language of the browser, because of that Javascript is one of the most popular programming languages in the world.

Why should you use Javascript? There are two answers. The first is that you don't have a choice. The Web has become an important platform for application development , and Javascript is the only language that is found in all browsers. The other answer is that, despite its deficiencies, JavaScript is really good. It's light-weight and expressive, and once you get the hang of it, functional programming is a lot of fun.

## A simple Testing Ground

Create a file called program.html:

    <html><body><pre><script src="program.js"> </script></pre></body></html>

Create a file called program.js:
    
    document.writeln('Hello world!');

# Grammar

This chapter introduces the grammar of Javscript, presenting a quick overview of how the language is structured.

## Whitespace

Whitespace is usually insignificant, but it's occasionally necessary to use whitespace to separate sequences of characters, for example: 

    var hello = "hi there";

We need to separate the _keyword_ **var**, from the variable name _hello_.

## Names

A Name is a letter, optionally followed by one of more letters, digits or underscores. There are few reserverd workds that cannot be used as a name, for example: abstract, boolean, break, byte, else, if, new, null, etc. 

Names are used for variables, parameters, proporties, operators and labels.


## Numbers 

A Number is something like 1, 1234, or 3.14.  Negative numbers are formed by using a dash prefix, like in -123, or -20.23.


## String

A string is a sequence of characters, like in "hello I'm a string". A string can wrapped in double quotes: "inside a double quote", or single quote 'like here'.

## Statements 

A program is made of a sequence of statements. Statements are executed from top to bottom. 

In Javascript there are conditional statements (_if_ and _switch_), looping statements (_while_, _for_, and _do_), and breaking statements (_break_, _return_). 

A _block_ in Javascript is a sequence of statements wrapped in curly brackets (_{_ ...  _}_ ).

## IF statement 

The _if_ statement alter how a program is executed, depending of the value of the _expression_. 

    if (1 == 0) { 
      document.write('they are equals');
    }
    else {
      document.write('they are not equals');
    }
# SWITCH statement 

Similar to the _if_ statement, the _switch_ statements handles more conditions.For example:

    switch (expression) {
      case "Oranges": 
        document.write('I like Oranges');
        break;
      case "Apples":
        document.write('I like Apples');
        break;
      case "Cherries":
        document.write('I like Cherries');
        break;
      default: 
        document.write("I don't think I like that");
    }

# WHILE statements

The _while_ statements performs a loop, as long as the expression is valid (or true). When the expression become _false_, the loop ends. Note, if the expression is not valid, the block is not executed at all. For example, this _while_ loop is executed;

    var counter = 0; 
    while (counter < 10){ 
      document.write("This message will be printed 10 times");
      counter = counter + 1;
    }

Another example, the following loop is not executed because the expression is not true. 

    var counter = 100; 
    while (counter < 10){
      document.write("Is this message shown?")
      counter = counter + 1;
    }
# DO staments

Very similar to the _while_ statements, but this time the code block is executed before, and the expression is checked at the end. Compare this code: 

    var counter = 0; 
    do {
      document.write("This message is printed 10 times");
      counter = counter + 1;
    } while (counter < 10);

You will see the message is actually printed 10 times. If we change to initial value of the variables: 

    var counter = 100; 
    do {
      document.write("This message is printed 10 times");
      counter = counter + 1;
    } while (counter < 10);

Now, you'll see how the message is printed once. That's because the expression _counter < 10_ is only checked after the block of code is executed.

# FOR Staments

The _for_ statement is another form of a _loop_. It has a specific syntax: 

    var counter;
    for(counter = 1; counter <=10 ; counter = counter + 1){ 
      document.write('This message is printed ' + counter + ' times');
    }


# Functions and Return statements

A function specify a sequence of instruction. Typically you want to pass some _parameters_ to the function. For example: 

    function sum(a, b) { 
      var total; 
      total = a + b;
      return total;
    }

If you want to return a value from a function, you can use the _return_ statement.

# Objects

We've already seen few basic data types in Javascript. Numbers (12, 123 for example), Strings ("Hi there", "John Smith" for example), Booleans (true and false).

## Object definition
Objects is an important data type too. We use _objects_ as a container for a group of _basic_ data types. For example, we might want to create an object to store the details of a _User_; 

    var user = {
      name: 'Thomas A. Anderson',
      nickname: 'Neo',
      gender: 'Male',
      height: '1.85',
    }

Also, we might want to create an object to store the details of a venue:

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


Note, we can also insert an object inside another object (see the _rating_ object?).

## Access the data

After the object has been initialised, we can now access its data using the following notation: 

    var name; 
    name = venue.name;

    var food_rating;
    food_rating = venue.ratings.food;


## Update the values


We can easily update the objects attributes:

    venue.name = 'Casa Italia';

We can also add more attributes in the same way: 

    venue.telephone = '0123456789';


# Arrays 

Arrays are used to store a sequence of objects or basis types (such as Numbers and String). Let's see few examples: 

    var names = ['Trinity','Neo','Agent Smith','Morpheus'];

We could also define an array to store a sequence of numbers: 

    var ratings =[1,2,3,4,5,6];

The first element of the array _always_ starts at zero position. If we want to get the first element, we need to use the square brackets notation:
    
    names[0]

This will return the string 'Trinity'. If we want to access the second element: 

    names[1]


In Javascript _Arrays_ have a lenght method:

    names.lenght 
    ratings.lenght


We can use the _lenght_ inside a loop for example:

    var position;
    for(position = 0; position < names.lenght; position = position + 1){
      document.write(names[position]);
    }



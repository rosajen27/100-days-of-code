# 100 Days Of Code - Log

Udemy Course: The Complete JavaScript Course 2021 by Jonas Schmedtmann

-----------------------------------------------------------------------------------------------------------------
### Day 1: April 15, 2021

**Today's Progress**: Spending some time this week revewing and studying how JavaScript works behind the scenes in order to solidify previously learned concepts. 

Today's study session included: 
    1. JavaScript Engine and Runtime
    2. Execution Context and the Call Stack
    3. Scope and The Scope Chain.


-----------------------------------------------------------------------------------------------------------------


### Day 2: April 16, 2021

**Today's Progress**: Spending some time this week revewing and studying how JavaScript works behind the scenes in order to solidify previously learned concepts. 

Today's study session included: 
    1. Variable Environment: Hoisting and The TDZ


-----------------------------------------------------------------------------------------------------------------


### Day 3: April 17, 2021

**Today's Progress**: Spending some time this week revewing and studying how JavaScript works behind the scenes in order to solidify previously learned concepts. 

Today's study session included: 
    1. The this Keyword


-----------------------------------------------------------------------------------------------------------------


### Day 4: April 18, 2021

**Today's Progress**: Practiced destructuring arrays in isolation

**Thoughts**: Destructuring - ES6 Feature, a way of unpacking values from an array or an object into separate variables (to break a complex data structure down into a smaller data structure like a variable).

* Old way of retrieving elements of an array:


const = [2, 3, 4];


const a = arr[0]; → 2


const b = arr[1]; → 3


const c = arr[2]; → 4

* Array Destructuring


const = [2, 3, 4];


const [x, y, z] = arr; → 2 3 4 


-----------------------------------------------------------------------------------------------------------------


### Day 5: April 19, 2021

**Today's Progress**: Practiced destructuring objects in isolation

**Thoughts**:To destructure objects we use the curly braces. Then all we have to do is to provide the variable names that exactly match the property names that we want to retrieve from the object. The order of elements does not matter - so we do not have to manually skip elements like in an array. Helpful when retrieving elements from an object when using APIs


-----------------------------------------------------------------------------------------------------------------


### Day 6: April 20, 2021

**Today's Progress**: Practiced implementing The Spread Operator (...) in isolation

**Thoughts**: We can use the spread operator to basically expand an array into all its elements (unpacking all the array elements at once)


const arr = [7, 8, 9];


const badNewArr = [1, 2, arr[0], arr[1], arr[2]];


console.log(badNewArr); → [1, 2, 7, 8, 9]



const newArr = [1, 2, ...arr];
console.log(newArr); → [1, 2, 7, 8, 9]



Same exact results. What the spread operator does is to basically take all the values out of this arr array and then write them individually as if we wrote 7, 8, 9 manually.


-----------------------------------------------------------------------------------------------------------------


### Day 7: April 21, 2021

**Today's Progress**: The Spread Operator, continued. with a focus on Objects

**Thoughts**: works in the same way with objects as it does with arrays. For example, if you wanted to make a shallow copy of an object named restaurant and then change the name property:


const restaurant = {


	name: “Classico Italiano”,


	categories: [“Italian”, “Pizzaria”, “Vegetarian, “Organic”],


}


const restaurantCopy = {...restaurant};


restaurantCopy.name = “Ristorante Roma”;


console.log(restaurantCopy.name); → Ristorante Roma


console.log(restaurant.name); → Clasicco Italiano


-----------------------------------------------------------------------------------------------------------------


### Day 8: April 22, 2021

**Today's Progress**: Rest Pattern and Parameters

**Thoughts**: The rest pattern looks exactly like the spread operator. It has the same syntax with the three dots, but it actually does the opposite of the spread operator.


We used the spread operator to build new arrays or to pass multiple values into a function. In both cases we can use the spread operator to expand an array into individual elements.


Now the rest pattern uses the exact same syntax, however, to collect multiple elements and condense them into an array.


Spread operator because it is on the right side of the equal sign


const arr = [1, 2, ...[3, 4]];


Rest operator because it is on the left side of the equal sign


const [a, b, ...others] = [1, 2, 3, 4, 5];


console.log(a, b, others); → 1 2 [3, 4, 5]



Can also work within functions, to accept any number of parameters:


const add = function(...numbers) {


	let sum = 0;


	for(let i = 0; i < numbers.length; i++) sum+=numbers[i];


	console.log(sum);


}




add(2, 3); → 5


add(5, 3, 7, 2); → 17


add(8, 2, 5, 3, 2, 1, 4); → 25


-----------------------------------------------------------------------------------------------------------------


### Day 9: April 23, 2021

**Today's Progress**: Short Circuiting (&& and ||)

**Thoughts**: In the case of the OR operator, short circuiting means that if the first value is a truthy value, it will immediately return that first value. 


In the case of the AND operator, it works in the exact opposite way of the OR operator. The AND operator short circuits when the first value is falsy, and then immediately returns that falsy value without even evaluating the second operand.


-----------------------------------------------------------------------------------------------------------------


### Day 10: April 24, 2021

**Today's Progress**: The Nullish Coalescing Operator (??)

**Thoughts**: The Nullish Coalescing Operator works with the idea or with the concept of nullish values instead of falsy values. Nullish values are null and undefined. It does not include zero or the empty string.


-----------------------------------------------------------------------------------------------------------------


### Day 11: April 25, 2021

**Today's Progress**: Looping Arrays using the for of loop

**Thoughts**: This loop will automatically loop over the entire array, and in each iteration, it will give us access to the current array element.


for (const item of menu) console.log(item);


→ results in printing each menu item separately in the console



What if we also wanted the current index and not just the current element?


for (const item of menu.entries()) {
	console.log(item);
}


→ results in printing the index of each menu item AND the menu item separately in the console (ex: [0, “Focaccia”] )


-----------------------------------------------------------------------------------------------------------------


### Day 12: April 26, 2021

**Today's Progress**: Looping Objects: Keys, Values, Entries

**Thoughts**:We have different options, depending on what exactly we want to loop over. Do we want to loop over the object’s property names, values, or both?


Looping over property names (aka keys):


const properties = Object.keys(openingHours);


let openStr = `We are open on ${properties.length} days: `;



for (const day of properties) {
	openStr += `${day}, `;
}


console.log(openStr);


→ We are open on 3 days: thu, fri, sat,


Looping over property values:


const values = Object.values(openingHours);


console.log(values);


→ 0: {open: 12, close: 22}


→ 1: {open: 11, close: 23}


→ 2: {open: 0, close: 24}



Entries() (names plus the values together):


const entries = Object.entries(openingHours);


console.log(entries);


→ 0: [“thu”, {...}]


→ 1: [“fri”, {...}]


→ 2: [“sat”, {...}]


----------------------------------------------------
for (const [day, {open, close}] of entries) {


	console.log(`On ${day} we open at ${open} and close at ${close});

    
}


→ On thu we open at 12 and close at 22


→ On fri we open at 11 and close at 23


→ On sat we open at 0 and close at 24


-----------------------------------------------------------------------------------------------------------------


### Day 13: April 27, 2021

**Today's Progress**: Sets

**Thoughts**: A set is a collection of unique values. So that means that a set can never have any duplicates.
Sets are also iterables, so you can loop over them.


In sets, there are no indexes, so there is no way of getting values out of a set. If your goal is to actually store values in order and then retrieve it, then the best use case is to just use an array.



const ordersSet = new Set([“Pasta”, “Pizza”, “Pizza”, “Risotto”, “Pasta”, “Pizza”]);


console.log(ordersSet);


→ Set(3) {“Pasta”, “Pizza”, “Risotto”} All the duplicates are gone. 


Also works with strings


console.log(new Set(“Jenny”)); → Set(5) {“J”, “e”, “n”, “n”, “y”}


We can get the size of a set


console.log(ordersSet.size); → 3



We can check if a certain element is in a set


console.log(ordersSet.has(“Pizza”); → true 



We can add new elements to a set


ordersSet.add(“Garlic Bread”);



We can also delete elements


ordersSet.delete(“Risotto”);


-----------------------------------------------------------------------------------------------------------------


### Day 14: April 28, 2021

**Today's Progress**: Maps Fundamentals

**Thoughts**: (More useful than sets), A map is a data structure that we can use to map values to keys. So, just like an object, data is stored in key value pairs in maps.  
The big difference between objects and maps is that in maps, the keys can have any type (it can even be objects, arrays, or other maps). Meanwhile, in objects the keys are basically always strings.
The easiest way to create a map is to actually create an empty map. Then you fill up the map with the set method.



const rest = new Map();


rest.set(“name”, “Classico Italiano”);


rest.set(1, “Firenze, Italy”);


rest.set(2, “Lisbon, Portugal”);


rest.set(“categories”, [“Italian”, “Pizzeria”, “Vegetarian”, “Organic”]);


	.set(“open”, 11)


	.set(“close”, 23)


	.set(true, “We are open”)


	.set(false, “We are closed”);



// example: compare the time and see if restaurant is open or closed
const time = 21;


console.log(rest.get(time > rest.get(“open”) && time < rest.get(“close”)));


→ We are open


-----------------------------------------------------------------------------------------------------------------


### Day 15: April 29, 2021

**Today's Progress**: Maps Iteration

**Thoughts**: There is another way of populating a new map without having to use the set method.

const question = new Map([


	[“question”, “What is the best programming language in the world?],


	[1, “C”],


	[2, “Java”],


	[3, “JavaScript”],


	[“correct”, 3],


	[true, “Correct!”],


	[false, “Try again!”],


]);


console.log(question);


// Quiz App


console.log(question.get(“question));


for (const [key, value] of question) {


	if(typeof key === “number”) console.log(`Answer ${key}: ${value}`);


}


const answer = Number(prompt(“Your answer?”));


console.log(answer);



console.log(question.get(question.get(“correct”) === answer));


→ Correct!


-----------------------------------------------------------------------------------------------------------------


### Day 16: April 30, 2021

**Today's Progress**: Which data structure to use?

**Thoughts**: There are essentially three sources of data.

1. From the program itself: Data written directly in source code

2. From the UI: Data input from the user data written in the DOM

3. From external sources: Data fetched for example from web API


There a four built in data structures in JavaScript.

Simple list? Use Arrays or Sets

Key/Value pairs? Use Objects or Maps (keys allow us to describe values)

Data from web APIs usually are in JSON

JSON is essentially just text, but it can easily be converted to JavaScript objects because it uses the same formatting as JavaScript objects and arrays.


-----------------------------------------------------------------------------------------------------------------


### Day 17: May 1, 2021

**Today's Progress**: Arrays vs. Sets

**Thoughts**: Arrays:

Use when you need ordered list of values (might contain duplicates)

Use when you need to manipulate data


Sets:

Use when you need to work with unique values

Use when high-performance is really important

Use to remove duplicates from arrays


Sets are not meant to replace arrays, but rather to compliment them whenever we are dealing with unique values.


-----------------------------------------------------------------------------------------------------------------


### Day 18: May 2, 2021

**Today's Progress**: Objects vs. Maps

**Thoughts**: Objects:

More traditional key/value store (“abused” objects)

Easier to write and access values with . and []


Maps:

Before performance

Keys can have any data type

Easy to iterate

Easy to compute size


As a conclusion, you should use maps when you simply need to map keys to values and also when you need keys that are not strings.


If you need functions as values, then you should absolutely use an object for that. In objects, these functions are called methods and you can use the this keyword to access properties of the same object, which is impossible in maps. Also, when working with JSON data, you will probably be using objects for that as well, unless you then want to convert the objects to maps (but that is something that we usually do not do)


-----------------------------------------------------------------------------------------------------------------


### Day 19: May 3, 2021

**Today's Progress**: Strings

**Thoughts**: Just like in arrays, we can get the character of a string at a certain position. We can also read the length properties of strings, just like we can in arrays. 


const plane = "A320";

console.log(plane[0]); --> A

console.log(plane.length) --> 4


Strings also have methods and some of them are quite similar to the array methods (Strings are also zero based). One good use case is to extract part of a string using the slice method (the slice method needs indexes as arguments).


console.log(plane.indexOf("0")); --> A

const airline = "TAP Air Portugal"

console.log(plane.slice(4)); --> Air Portugal

console.log(plane.slice(4, 7)); --> Air

console.log(airline.slice(-2)); --> al


console.log(airline.slice(0, airline.indexOf(" "))); --> Tap


** Note: This does not change the underlying string, because it is impossible to mutate strings. They are primitives.


-----------------------------------------------------------------------------------------------------------------


### Day 20: May 4, 2021

**Today's Progress**: String Methods (continued)

**Thoughts**: 

// Changing the case of a string

console.log(airline.toLowerCase()); --> tap air portugal

console.log(airline.toUpperCase()); --> TAP AIR PORTUGAL


// Remove extra whitespace

const email = "    hello@gmail.com \n";

const trimmedEmail = email.trim();

console.log(trimmedEmail); --> hello@gmail.com


// Replace

const priceGB = "288,97";

const priceUS = priceGB.replace(",", "."); --> 288.97


// Booleans

const plane = "A320neo";

console.log(plane.includes("A320")); --> true

console.log(plane.startsWith("Air")); --> false


-----------------------------------------------------------------------------------------------------------------


### Day 21: May 5, 2021

**Today's Progress**: String Methods (continued)

**Thoughts**: 

// Split and Join

console.log(“a+very+nice+string”.split(“+”)); → [“a”, “very”, “nice”, “string”]

console.log(“Jennifer Rosa”).split(“ “)); → [“Jennifer”, “Rosa”]


Real World Example:

const [firstName, lastName] = “Jennifer Rosa”.split(“ “); 

const newName = [“Ms.”, firstName, lastName.toUpperCase()].join(“ “);

console.log(newName); → Ms. Jennifer ROSA


// Create a function that capitalizes the first letter of a name

const capitalizeName = function(name) {

	const names = name.split(“ “);

	Const namesUpper = [];


	for (const n of names) {

		namesUpper.push(n[0].toUpperCase() + n.slice(1));

	}

	console.log(namesUpper.join(“ “));

};


capitalizeName(“jennifer rosa”); → Jennifer Rosa


// Padding

const message = “Go to gate 23!”;

console.log(message.padStart.(25, “+”)); → +++++++++++Go to gate 23!

console.log(message.padEnd.(25, “+”)); → Go to gate 23!+++++++++++


// Masking

const maskCreditCard = function(number) {

	const str = String(number);

	const last = str.slice(-4);

	Return last.padStart(str.length, “*”);

}

console.log(maskCreditCard(4337846386467384)); → ************7384


// Repeat

const newMessage = “Bad Weather.. All Departures Delayed… ”;

console.log(newMessage.repeat(3)); → Bad Weather.. All Departures Delayed… Bad Weather.. All Departures Delayed… Bad Weather.. All Departures Delayed… 


-----------------------------------------------------------------------------------------------------------------


### Day 22: May 6, 2021

**Today's Progress**: Functions: Default Parameters

**Thoughts**: 
Sometimes it is useful to have functions where some parameters are set by default, this way we do not have to pass them in manually, in case we don’t want to change the default.


const bookings = [];

const createBooking = function(flightNum, numPassengers, price) {

	const booking = {

		flightNum,

		numPassengers,

		price

	}

	console.log(booking);

	bookings.push(booking);

}

createBooking(“LH123”); 

→ {flightNum: “LH123”, numPassengers: undefined, price: undefined}


What we see here was that the numPassengers are the price are set to undefined, because we didn’t specify them. Now we can use short circuiting to our advantage, because we know that these are faulty values. Let’s say we want to set the number of passengers to one by default…


numPassengers = numPassengers || 1;

price = price || 199;


This works because whenever this is a falsy value (which undefined is), then the result of the OR operator will be the second operand. 


Default values can contain any expression. For example, we can multiply x 1.2. We can also use the value of the other parameters that were set before it. 

// Example, you can say the price will be calculated based on the number of passengers
price = 199 * numPassengers


-----------------------------------------------------------------------------------------------------------------


### Day 23: May 7, 2021

**Today's Progress**: Functions: How Passing Arguments Works - Value vs.
Reference

**Thoughts**: When we pass a primitive type as an argument on a function, the function makes a copy of the ORIGINAL VALUE, and works with it.


On the other hand, when we pass an object as an argument on a function, the function makes a copy of the REFERENCE that points to the place of the memory where the object is stored. This copy is a value itself, not a reference. Because of all of this, the original object can be modified from inside of a function.


- In programming languages, Arguments can be passed by value, or passed by reference

- JS does not have passing by reference, only passing by value

- So, when we pass primitive values, the function works with a value, which is a copy of the original value

- When we pass an object, the function works with a value that address to the spot where the original object is in the memory (still is not a reference)


-----------------------------------------------------------------------------------------------------------------


### Day 24: May 8, 2021

**Today's Progress**: Functions: First Class and Higher Order Functions

**Thoughts**: JavaScript is a language that has first class functions, which in technical terms means that functions are so called first citizens. In practice, this means that functions are simply values. Functions are just another “type” of object. And since objects are values, functions are values too. 

And since functions are values, we can do many interesting things with them like storing them in variables or object properties.

const add = (a, b) => a + b;

const counter = {

	value: 23,

	inc: function() { this.value++; }


We can also pass functions as arguments to other functions.

const greet = () => console.log(“Hey Jennifer”);

btnClose.addEventListener(“click”, greet)


We can also return a function from another function.


We can call methods on functions

counter.inc.bind(someOtherObject);


The fact that JavaScript has first-class functions makes it possible for us to use and write higher order functions. A higher order function is either a function that receives another function as an argument or a function that returns a new function.

const greet = () => console.log(“Hey Jennifer”);

btnClose.addEventListener(“click”, greet)


First class functions are just a feature that a programming language either has or does not have. All it means is that all functions are values. There are no first class functions in practice (it’s just a concept).


There are however higher order functions in practice, which are possible because the language supports first class functions.


-----------------------------------------------------------------------------------------------------------------


### Day 25: May 9, 2021

**Today's Progress**: Callback Functions, Functions Calling Functions, and the Call and Apply Method

**Thoughts**: Functions Accepting Callback Functions

Callback functions are functions that we do not call ourselves. But instead, we call JavaScript to basically tell them later. In this case, it is the transformer function that will callback the upperFirstWord and oneWord functions.


const oneWord = function(str) {

	return str.replace(/ /g, “”).toLowerCase();

}


const upperFirstWord = function(str) {

	const [first, ...others] = str.split(“ “);

	return [first.toUpperCase(), ...others].join(“ “);

}


// higher order function (a function that takes in another function)

const transformer = function(str, fn) {

	console.log(`Original string: ${str});

	console.log(`Transformed string: ${fn(str)}`);

	console.log(`Transformed by: ${fn.name}`);

}

transformer(“JavaScript is the best!”, upperFirstWord);

→ Original string: JavaScript is the best!

→ Transformed string: JAVASCRIPT is the best!

→ Transformed by: UpperFirstWord


transformer(“JavaScript is the best!”, oneWord);

→ Original string: JavaScript is the best!

→ Transformed string: javascriptisthebest!

→ Transformed by: oneWord


Why are callback functions helpful? The first big advantage of this is that it makes it easy to split up our code into more reusable and interconnected parts. Callback functions also allow us to create abstraction (hide the detail of some code implementation because we don’t really care about all of that detail. This allows us to think about problems at a higher, more abstract level).


Functions Returning Functions

What is the point of having a function returning another function? It is extremely useful in some situations, especially if we’re using an important programming paradigm called functional programming. 


const greet = function(greeting) {

	return function(name) {

		console.log(`${greeting} ${name}`);

	}

}

const greeterHey = greet(“Hey”);

greeterHey(“Jennifer”);

→ Hey Jennifer


greet(“Hello”)(“Jen”);

→ Hello Jen


The Call and Apply Methods

const jetblue = {

	airline: “Jetblue”,

	iataCode: “JB”,

	bookings: [],

	book(flightNum, name) {

		console.log(`${name} booked a seat on ${this.airline} flight ${this.iataCode}${flightNum}`);

	this.bookings.push({flight: `${this.iataCode}${flightNum}`, name});

	},

};

jetblue.book(239, “Jennifer Rosa”);

jetblue.book(635, “John Smith”);

→ Jennifer Rosa booked a seat on Jetblue flight JB239

→ John Smith booked a seat on Jetblue flight JB635

console.log(jetblue);

→ {airline: “Jetblue”, iataCode: “JB”, bookings” Array(2), book: f}


// new airline

const eurowings = {

	name: “Eurowings”,

	iataCode: “EW”,

	bookings: [],

};


const book = jetblue.book;


book(23, “John Snow”); → Uncaught TypeError: Cannot read property ‘airline’ of undefined at book


So, how do we tell JavaScript that we want to create a booking on the new Eurowings airline? We need to tell JavaScript explicitly what the this keyword should be like. There are three function methods that can do this: call, apply, bind.


book.call(eurowings, 23, “John Snow”);

console.log(eurowings);

→ {name: “Eurowings”, iataCode: “EW”, bookings: Arr(1)}

	Bookings: Array(1)

	0: {flight: “EW23”, name: “John Snow”}


Recap: We called the call method, which called the book function, with the this keyword set to eurowings. This allows us to manually and explicitly set the this keyword of any function that we want to call.


The apply method does basically the same thing. The only difference is that the apply method does not receive a list of arguments. Instead, it will take an array of the arguments.


-----------------------------------------------------------------------------------------------------------------


### Day 26: May 10, 2021

**Today's Progress**: The Bind Method

**Thoughts**: Just like the Call Method, bind also allows us to manually set the this keywords for any function call. Now, the difference is that bind does not immediately call the function. Instead, it returns a new function where the this keyword is bound. So it is set to whatever value we pass into bind. 

const eurowings = {
	name: “Eurowings”,
	iataCode: “EW”,
	bookings: [],
};
const book = jetblue.book;

const bookEW = book.bind(eurowings); 
// note: this will NOT call the book function. Instead, it will return a new function where the this keyword will always be set to Eurowings. 

bookEW(23, “Steven Williams”); 
→ Steven Williams booked a seat on Eurowings flight EW23
// note: this now looks like the normal book function call again. That is because this function already has the this keyword set in stone basically. So we no longer need to specify the this keyword again. 
The bind method is really useful because we could now go ahead and do the same for multiple airlines. So creating one booking function for each of the airlines. This then makes it easier to book a flight for each of the airlines if we have to do it multiple times.

const bookEW = book.bind(eurowings); 
const bookJB = book.bind(jetblue);

// Bind Method with Event Listeners
In an event listener function, the this keyword always points to the element on which that handler is attached to. In this case, jetblue.buyPlane is the handler function and it is attached to the document.querySelector(“.buy”) button element. Therefore, inside of the handler function, the this keyword will point to the button element. 

In order for the this keyword to point to the jetblue object instead, we need to manually define the this keyword by passing in a function with the bind method. Bind is going to return a new function, so the this keyword should be jetblue so that’s exactly what we define. So the end result is that the number of planes should increase each time we press the button.


jetblue.planes = 300;
jetblue.buyPlane = function() {
	console.log(this);
	this.planes++;
	console.log(this.planes);
};

document
	.querySelector(“.buy”)
	.addEventListener(“click”, jetblue.buyPlane.bind(jetblue));


// Partial Application
Partial application means that we can preset parameters.
const addTax = (rate, value) => value + value * rate;
console.log(addTax(0.1, 200));
→ 220

We can use the bind method to preset the rate to always be 23% for example.
const addVAT = addTax.bind(null, 0.23);
console.log(addVAT(100));
→ 123


-----------------------------------------------------------------------------------------------------------------


### Day 27: May 11, 2021

**Today's Progress**: Immediately Invoked Function Expressions (IIFE)

**Thoughts**: Sometimes in JavaScript, we need a function that is only executed once, and then never again. So basically a function that disappears right after it’s called once. We can trick JavaScript into thinking that this anonymous function is an expression by wrapping it in parentheses and then calling it.


(function() {

	console.log(“This will never run again.”);

})();


(() => console.log(“This will ALSO never run again”))();


Why was this pattern invented? We already know that functions create scopes. It is important to note that one scope does not have access to variables from an inner scope. Therefore, we say that all data defined inside a scope is private and encapsulated. Data encapsulation and data privacy are important concepts in programming.


Many times we need to protect our variables, from being accidentally overwritten by some other parts of the program, or even with external scripts or libraries.


-----------------------------------------------------------------------------------------------------------------


### Day 28: May 12, 2021

**Today's Progress**: Closures

**Thoughts**: A closure is not a feature that we explicitly use. We don’t create closures manually, it happens automatically in certain situations. 


const secureBooking = function() {

	let passengerCount = 0;

	return function() {

		passengerCount++;

		console.log(`${passengerCount} passengers`);

	}
}

const booker = secureBooking();



A closure makes a function remember all the variables that existed at the function’s “birth place”.


A function always has access to the variable environment of the execution context in which it was created, even after that execution context is gone. The closure is then basically this variable environment attached to the function, exactly as it was at the time and place that the function was created. 


In this example, the Booker function has access to the passengerCount variable because it’s basically defined in the scope in which the Booker function was actually created. So in a sense, the scope chain is actually preserved through the closure, even when a scope has already been destroyed because its execution context is gone. This means that even though the execution context has actually been destroyed, the variable environment somehow keeps living somewhere in the engine. 


 (function () {

 const header = document.querySelector('h1');

 header.style.color = 'red';


 document.querySelector("body").addEventListener("click", function() {

     header.style.color="blue";

 })

 })();


How does the callback function get access to the header variable? The explanation is the closure. The header is in the "backpack" of this function.


-----------------------------------------------------------------------------------------------------------------


### Day 29: May 13, 2021

**Today's Progress**: Array methods

**Thoughts**: Why do arrays have methods? Methods are simply functions that we can call on objects. So basically, they are functions attached to objects. So if we have array methods, that means that arrays themselves are also objects. And so these array methods are simply functions that are attached to all arrays that we create in JavaScript.



Slice Method: we can extract part of any array, but without changing the orginial array.


let arr = ["a", "b", "c", "d", "e"];


console.log(arr.slice(2)); --> ["c", "d", "e"]

console.log(arr.slice(2, 4)); --> ["c", "d"]

console.log(arr.slice(-2)); --> ["d", "e"]

console.log(arr.slice(-1)); --> ["e"]

console.log(arr.slice(1, -2)); --> ["b", "c"]

console.log(arr.slice()); --> ["a", "b" "c", "d", "e"] //shallow copy

SAME AS DOING console.log([...arr]);



Splice Method: works similar to the slice method, but the fundamental difference is that it does actually change/mutate the original array



Reverse Method: Reverses the order of the array. This method also mutates the original array.

const arr2 = ["j", "i", "h", "g", "f"];

console.log(arr2.reverse()); --> ["f", "g", "h", "i", "j"]



Concat Method: Concatinates two arrays. This method does not mutate the original array.

const letters = arrconcat(arr2);

console.log(letters); --> ["a", "b" "c", "d", "e", "f", "g", "h", "i", "j"]

SAME AS DOING: console.log([...arr, ...arr2]);



Join Method: Results with a string with the seperator that we specify.

console.log(letters.join(" - ")); --> a - b - c - d - e - f - g - h - i - j 


-----------------------------------------------------------------------------------------------------------------


### Day 30: May 14, 2021

**Today's Progress**: Looping Arrays: forEach

**Thoughts**: Let's say that we wanted to loop over an array, in order to print a message for each movement. In this scenario, positive values are deposits and negative values are withdrawals.



const movements = [200, 450, -400, 3000, -650, -130, 70, 1300];



// for of loop


for (const movement of movements) {

	if(movement > 0) {

		console.log(`You deposited ${movement}`)

	} else {

		console.log(`You withdrew ${Math.abs(movement)}`);

	}

}

--> You deposited 200

--> You deposited 450

--> You withdrew 400 ... etc. etc.



// forEach

movements.forEach(function(movement) {

	if(movement > 0) {

		console.log(`You deposited ${movement}`)

	} else {

		console.log(`You withdrew ${Math.abs(movement)}`);

	}

}); --> // Same result as for of loop


What if we needed access to a counter variable? 

// For of

for (const [i, movement] of movements.entries()) {

	if(movement > 0) {

		console.log(`Movement ${{i + 1}: You deposited ${movement}`)

	} else {

		console.log(`Movement ${{i + 1}: You withdrew ${Math.abs(movement)}`);

	}

});

--> Movement 1: You deposited 200

--> Movement 2: You deposited 450

--> Movement 3: You withdrew 400 ... etc. etc.


// for Each

movements.forEach(function(movement, index, array) {

	if(movement > 0) {

		console.log(`Movement ${{index + 1} You deposited ${movement}`)

	} else {

		console.log(`Movement ${{index + 1} You withdrew ${Math.abs(movement)}`);

	}

}); --> // Same result as for of loop



When should you use for each and when should you use for of loop? One fundamental difference between the two of them is that you cannot break out of a forEach loop. So the continue and break statements do not work in a forEach loop at all. So instead, forEach will always loop over the entire array and there is nothing you can do about it. 

So if you really need to break out of a loop, then you have to keep using the for of loop, but other than that then it just comes down to personal preference.


-----------------------------------------------------------------------------------------------------------------


### Day 31: May 15, 2021

**Today's Progress**: forEach with Maps and Sets

**Thoughts**: We can call forEach on maps.


const currencies = new Map([

	["USD", "United States dollar"],

	["EUR", "Euro],

	["GBP", "Pound sterling"],

]);


currencies.forEach(function(value, key, map) {

	console.log(`${key}: ${value}`);

}); 


--> USD: United States Dollar

--> EUR: Euro

--> GBP: Pound sterling


We can fall forEach on sets.


const currenciesUnique = new Set(["USD", "GBP", "USD", "EUR", "EUR"]);

console.log(currenciesUnique);

--> {"USD", "GBP", "EUR"}

currenciesUnique.forEach(function(value, key, map) {

	console.log(`${key}: ${value}`);
});

--> USD: USD

--> GBP: GBP

--> EUR: EUR

The key here is exactly the same as the value. Why is that? A set doesn't have keys and it doesn't have indexes either. So there is no value that would make sense for the key.


-----------------------------------------------------------------------------------------------------------------


### Day 32: May 16, 2021

**Today's Progress**: Begin developing Bankist App

**Thoughts**: Through the development of this application, I will have the opportunity to apply concepts I have learned about functions and arrays. Bankist is a fictitious and minimalist online banking application that allows the user to:


- Log in with a username and password
- View and sort their monetary movements
- Transfer money to another account
- Request a loan from the bank
- Delete their account


GitHub Repo: https://github.com/rosajen27/bankist


-----------------------------------------------------------------------------------------------------------------

(Personal Note: I took several days off from coding last week due to an unexpected loss in the family. 💔)


-----------------------------------------------------------------------------------------------------------------


### Day 33: May 24, 2021

**Today's Progress**: Spent some time today reviewing previous learning about arrays in order to complete a coding challenge. 

Coding challenge provided by Jonas Schmedtmann's JavaScript Course.

**Thoughts**: Coding Challenge:


Julia and Kate are doing a study on dogs. So each of them asked 5 dog owners about their dog's age, and stored the data into an array (one array for each). For 
now, they are just interested in knowing whether a dog is an adult or a puppy. A dog is an adult if it is at least 3 years old, and it's a puppy if it's less than 3 years old.


Create a function 'checkDogs', which accepts 2 arrays of dog's ages ('dogsJulia' and 'dogsKate'), and does the following things:


- Julia found out that the owners of the first and the last two dogs actually have cats, not dogs! So create a shallow copy of Julia's array, and remove the cat ages from that copied array (because it's a bad practice to mutate function parameters)

- Create an array with both Julia's (corrected) and Kate's data

- For each remaining dog, log to the console whether it's an adult ("Dog number 1 is an adult, and is 5 years old") or a puppy ("Dog number 2 is still a puppy")

- Run the function for both test datasets


My solution:


const dogsJulia = [3, 5, 2, 12, 7];

const dogsKate = [4, 1, 15, 8, 3];


const dogsJulia2 = [9, 16, 6, 8, 3];

const dogsKate2 = [10, 5, 6, 1, 4];


const checkDogs = function (dogsJulia, dogsKate) {


  const dogsJuliaCopy = dogsJulia.slice(1, -2);

  const allDogs = dogsJuliaCopy.concat(dogsKate);


  allDogs.forEach(function (dog, i) {

    if (dog >= 3) {

      console.log(`Dog number ${i + 1} is an adult, and is ${dog} years old.`);

    } else {

      console.log(`Dog number ${i + 1} is still a puppy 🐶`);

    }

  });

}


checkDogs(dogsJulia, dogsKate);

checkDogs(dogsJulia2, dogsKate2);


-----------------------------------------------------------------------------------------------------------------


### Day 34: May 25, 2021

**Today's Progress**: Data Transformations: map, filter, reduce

**Thoughts**: In JavaScript, there are three big and important array methods that we use all the time to perform data transformations. These are methods that we use to create new arrays based on transforming data from other arrays. (Map, Filter, Reduce)


- Map Method: the map method is yet another method that we can use to loop over arrays. The map method is similar to the forEach method, but the map method creates a brand new array based on the original array. 


So essentially the map method takes an array, loops over that array and in each iteration, it applies a callback function that we specify on our code to the current array element.


We say that it maps the values of the original array to a new array and that's why this method is called map.


Map returns a new array containing the results of applying an operation on all original array elements.


Example: [3, 1, 4, 3, 2] <-- original array

Map: current * 2 = [6, 2, 8, 6, 4] <-- new array


- Filter Method: is used to filter for elements in the original array, which satisfies a certain condition.


Example: [3, 1, 4, 3, 2] <-- original array

Filter: current > 2 = [3, 4, 3] <-- filtered array


- Reduce Method: used to boil ("reduce") down all of the elements of the original array into one single value. An example of this can be to add all the elements of an array together. It can also be many other operations.

Example: [3, 1, 4, 3, 2] <-- original array

Reduce: accumulator + current = [13]


-----------------------------------------------------------------------------------------------------------------


### Day 35: May 26, 2021

**Today's Progress**: Polishing Portfolio, GitHub, and Resume

**Thoughts**: With 3 weeks left of the 2020-2021 school year, I will be utilizing this upcoming summer break as an opportunity to begin the application process. I aspire to transition from a k-6 educator to a front end web developer.

✨ Portfolio: https://rosajen27.github.io
👾 GitHub: https://github.com/rosajen27
📄 Resume: https://bit.ly/2Svsirg


-----------------------------------------------------------------------------------------------------------------


### Day 36: May 27, 2021

**Today's Progress**: The Map Method

**Thoughts**: The Map method is another way we can loop over arrays. Unlike forEach, the Map method will give us a brand new array. This new array will contain in each position the results of applying a callback function to the original array elements.


With the Map method - besides the current array element, we also get access to the current index as well as the whole array.


Applied this new knowledge into Bankist App Project

GitHub Repo: https://github.com/rosajen27/bankist

- Used the Map method to convert EUR to USD
- Used the Map method to return movement descriptions


-----------------------------------------------------------------------------------------------------------------


### Day 37: May 28, 2021

**Today's Progress**: Using the Map and forEach method to computer usernames for each account owner in Bankist App.

GitHub Repo: https://github.com/rosajen27/bankist

**Thoughts**: The username will be the initials of each of the four users.


const user = "Steven Thomas Williams"; // stw

const username = user.toLowerCase().split(" ").map
(function(name) {

  return name[0];

}).join("");


-----------------------------------------------------------------------------------------------------------------


### Day 38: May 29, 2021

**Today's Progress**: Using the Filter Method to filter out negative values (withdrawals) in Bankist App.

GitHub Repo: https://github.com/rosajen27/bankist

**Thoughts**: The Filter Method is used to filter for elements that satisfy a certain condition by using a callback function.


// filter out negative values (withdrawals)

const deposits = movements.filter(function(movement) {

	return movement > 0;
	
});


-----------------------------------------------------------------------------------------------------------------


### Day 39: May 30, 2021

**Today's Progress**: Using the Reduce Method to add multiple values (deposits and withdrawals) in Bankist App in order to determine global balance of the account.

GitHub Repo: https://github.com/rosajen27/bankist

**Thoughts**: The reduce method is used to boil down all the elements in an array to one single value.


// accumulator --> SNOWBALL

// 0 --> initial value

const balance = movements.reduce(function(accumulator, currentValue, i, arr) {

	console.log(`Iteration ${i}: ${accumulator}`);

	return accumulator + currentValue;
	
}, 0);


-----------------------------------------------------------------------------------------------------------------


### Day 40: May 31, 2021

**Today's Progress**: Practiced solving another coding challenge provided by Jonas Schmedtmann in order to practice Map, Reduce, and Filter methods.

**Thoughts**: Challenge: Create a function 'calcAverageHumanAge', which accepts an arrays of dog's ages ('ages'), and does the following things in order:


1. Calculate the dog age in human years using the following formula: if the dog is 
<= 2 years old, humanAge = 2 * dogAge. If the dog is > 2 years old, 
humanAge = 16 + dogAge * 4


2. Exclude all dogs that are less than 18 human years old (which is the same as 
keeping dogs that are at least 18 years old)


3. Calculate the average human age of all adult dogs


4. Run the function for both test datasets


My Solution:

const calcAverageHumanAge = function (ages) {

  // MAP

  const humanAges = ages.map(function (age) {

    if (age <= 2) {

      return age * 2;

    } else {

      return 16 + age * 4;

    }

  });


  // FILTER

  const adults = humanAges.filter(function (age) {

    return age > 18;

  });


  // REDUCE

  const averageAge = adults.reduce(function (accumulator, currentValue) {

    return accumulator + currentValue / adults.length;

  }, 0);

  return averageAge;

}


calcAverageHumanAge([5, 2, 4, 1, 15, 8, 3]);

calcAverageHumanAge([16, 6, 10, 5, 6, 1, 4]);


-----------------------------------------------------------------------------------------------------------------


### Day 41: June 7, 2021

**Today's Progress**: Practiced Chaining Methods together in Bankist App.

GitHub Repo: https://github.com/rosajen27/bankist

**Thoughts**: My next task with the Bankist App was to take all the movement deposits then convert them from Euros to Dollars and add them all up, so that we know exactly how much was deposited into the account in US dollars.


We could do each of these operations individually and store each result in a new variable OR instead, we can chain the methods.

We can only chain a method after another one, if the first one returns an array. 

const totalDepositsUSD = movements

  .filter(function (movement) {

    return movement > 0;

  }).map(function (movement) {

    return movement * eurToUSD;

  }).reduce(function (accumulator, movement) {

    return accumulator + movement;

  }, 0);


console.log(totalDepositsUSD);


You can inspect the current array at any stage of the 'pipeline' using the third parameter of the callback function


console.log(movements);

const totalDepositsUSD = movements

  .filter(function (movement) {

    return movement > 0;

  }).map(function (movement, index, array) {

    console.log(array)

    return movement * eurToUSD;

  }).reduce(function (accumulator, movement) {

    return accumulator + movement;

  }, 0);

console.log(totalDepositsUSD);


-----------------------------------------------------------------------------------------------------------------


### Day 42: June 8, 2021

**Today's Progress**: Continued to practiced Chaining Methods together in Bankist App.

GitHub Repo: https://github.com/rosajen27/bankist

**Thoughts**: Chained filter, map, and reduce methods to create calcDisplaySummary function in order to display a summary of all deposits, withdrawals and interest earned in the user's account. Interest only applies if balance is equal to 1 or greater.


Important Notes: 


We should not overuse chaining, and instead optimize it. Chaining many methods one after the other can cause performance issues if using large arrays. 

It is a bad practice in JavaScript to chain methods that mutate the underlying original array. An example of that is the splice or reverse methods. 


-----------------------------------------------------------------------------------------------------------------


### Day 43: June 9, 2021

**Today's Progress**: Solved a Chaining Methods Coding Challenge provided by Jonas Schmedtmann's JavaScript Course.

**Thoughts**: Challenge: Rewrite the 'calcAverageHumanAge' function from the previous challenge, but this time use chaining.


Test Data 1: [5, 2, 4, 1, 15, 8, 3]

Test Data 2: [16, 6, 10, 5, 6, 1, 4]


Solution:



// WRITTEN EXPLICITLY 

const calcAverageHumanAge = function (ages) {

  const avgAges = ages.map(function (age) {

    if (age <= 2) {

      return age * 2;

    } else {

      return 16 + age * 4;

    }

  }).filter(function (age) {

    return age >= 18;

  }).reduce(function (accumulator, currentValue, i, arr) {

    return accumulator + currentValue / arr.length;

  }, 0);



  return avgAges;

};



const avg1 = calcAverageHumanAge([5, 2, 4, 1, 15, 8, 3]);

const avg2 = calcAverageHumanAge([16, 6, 10, 5, 6, 1, 4]);

console.log(avg1, avg2);



// WRITTEN WITH ARROW FUNCTIONS

const calcAverageHumanAgeArrow = ages =>

  ages.map(age => (age <= 2 ? age * 2 : 16 + age * 4))

    .filter(age => age >= 18)

    .reduce((acc, age, i, arr) => acc + age / arr.length, 0);



const avg1Arrow = calcAverageHumanAgeArrow([5, 2, 4, 1, 15, 8, 3]);

const avg2Arrow = calcAverageHumanAgeArrow([16, 6, 10, 5, 6, 1, 4]);

console.log(avg1Arrow, avg2Arrow);


-----------------------------------------------------------------------------------------------------------------


### Day 44: June 10, 2021

**Today's Progress**: The Find Method

**Thoughts**: We can use the find method to retrieve one element of an array based on a condition. Just like the filter method, the find method also needs a callback function that returns a Boolean. The result will be either true or false. 


Unlike the filter method, the find method will actually not return a new array, but it will only return the first element in the array that satisfies this condition - not an array.


Usually the goal of the find method is to find exactly one element. 


// Using the Bankist App as an example...

// find the first negative movement (withdrawal)

movements.find(function(movement) {

	return movement < 0;

});


-----------------------------------------------------------------------------------------------------------------


### Day 45: June 11, 2021

**Today's Progress**: Implementing the log in feature to Bankist Application

GitHub Repo: https://github.com/rosajen27/bankist

**Thoughts**: Implemented an event handler that:

- prevents log in form from submitting (page reload)
- clear log in input fields after user is signed in
- displays UI and welcome message
- display movements, balance, and summary of corresponding account user logged in with
- dynamically use interest rate depending on the current user


-----------------------------------------------------------------------------------------------------------------


### Day 46: June 12, 2021

**Today's Progress**: Implementing transfers feature to Bankist Application

GitHub Repo: https://github.com/rosajen27/bankist

**Thoughts**: Implemented an event handler that:

- allows the user to transfer money from one account to another account
- subtracts amount transfered from current account
- adds amount transfered from current account to reciever account
- transfer can only happen if amount is greather than 0
- the current user needs to have enough money to execute the transfer
- user should also not be able to transfer money to own/same account


-----------------------------------------------------------------------------------------------------------------


### Day 47: June 13, 2021

**Today's Progress**: The findIndex Method

**Thoughts**: The the findIndex method works almost the same way as find. But as the name says, findIndex returns the index of the found element and not the element itself. To delete an element from an array, we use the splice method, but for the splice method, we need the index at which we want to delete, so we use the findIndex method.


The findIndex method is similar to the indexOf method. However, the big difference here is that with indexOf we can only search for a value that is in the array. Example: .indexOf(23) - if the array contains the 23, then it's true and if not, then it's false.


But on the other hand, with findIndex we can create a complex condition, such as the one implemented in the Bankist App to delete user from data:


const index = accounts.findIndex(function (account) {

      return account.username === currentAccount.username;

    });


GitHub Repo: https://github.com/rosajen27/bankist


-----------------------------------------------------------------------------------------------------------------


### Day 48: June 14, 2021

**Today's Progress**: Implementing the log out feature to Bankist Application

GitHub Repo: https://github.com/rosajen27/bankist

**Thoughts**: When the user logs out or deletes their account, input fields should be cleared and the UI should be hidden.


-----------------------------------------------------------------------------------------------------------------


### Day 49: June 15, 2021

**Today's Progress**: Using the some and every methods within Bankist Application in order to implement bank loan functionality.

GitHub Repo: https://github.com/rosajen27/bankist

**Thoughts**: SOME METHOD - Let's say that we would like to know if there has been any deposits (positive movements) on a specific account - so any number above zero.


const anyDeposits = movements.some(function(movement) {

	return movement > 0;

});

console.log(anyDeposits); --> true (this is because there are some movements in the account that is a deposit)


In conclusion, if there is any value for which this condition is true, then the some method will return true.


-----------------------------------------------------------------------------------------------------------------


EVERY METHOD - The every method is pretty similar to the some method, but the difference between them is that every only returns true if all of the elements in the array satisfy the condition that we pass in.

If every element passes the test in our callback function, only then the every method returns true, hence the name.

const everyDeposits = movements.every(function (movement) {

	retun movement > 0;

});

console.log(everyDeposits); --> false (this is because not every single movement in the account is a deposit)


-----------------------------------------------------------------------------------------------------------------


The loan functionality will allow the user to:

- request a loan
- bank will grant a loan if there is at least one deposit in the account with at least 10% of the requested loan amount


-----------------------------------------------------------------------------------------------------------------


### Day 50: June 16, 2021

**Today's Progress**: ✨ 50 days ✨ - flat method


**Thoughts**: What if we wanted to take all these elements in the separate arrays, and put them all together in one big array? We can use the flat method. Using the flat method will remove the nested arrays and flatten the array.


const arr = [[1, 2, 3], [4, 5, 6], 7, 8]];

console.log(arr.flat()); --> [1, 2, 3, 4, 5, 6, 7, 8]


What if we have an array which is even deeper nested?


const arrDeep = [[[1, 2], 3], [4, [5, 6]], 7, 8]];

console.log(arrDep.flat()); --> [Array(2), 3, 4, Array(2), 7, 8]


This result still contains the two inner arrays. This means that the flat method only goes one level deep, when flattening the array. We can fix that by using the depth argument. 1 is the default depth.


const arrDeep = [[[1, 2], 3], [4, [5, 6]], 7, 8]];

console.log(arrDep.flat(2)); --> [1, 2, 3, 4, 5, 6, 7, 8]


-----------------------------------------------------------------------------------------------------------------


GitHub Repo: https://github.com/rosajen27/bankist

With the Bankist App, let's say that the bank itself wants to calculate the overall balance of all the movements of all the account.


The first thing to do is to take the movements out of the accounts array and put them all into one array.


const accountMovements = accounts.map(function 

(account) {

	return account.movements

});

console.log(accountMovements); --> // this will return a nested structure (an array which contains other arrays)


const allMovements = accountMovements.flat();
console.log(allMovements); --> // this will return a single array with all movements together


Then all we have to do is add them all together.


const overallBalance = allMovements.reduce(function
(accumulator, currentMovement) {

	return accumulator + currentMovement

}, 0);

console.log(overallBalance); --> 17840



-----------------------------------------------------------------------------------------------------------------


### Day 51: June 17, 2021

**Today's Progress**: sorting arrays


**Thoughts**: Sorting Arrays will sort arrays in ABC order. It will also mutate the original array. The sort method also does the sorting based on strings. So basically, what it does is to convert everything to strings and then it does the sorting itself.


// Strings

const owners = ["Jonas", "Zach", "Adam", "Martha"];

console.log(owners.sort()); --> ["Adam", "Jonas", "Martha", "Zach"];


// Numbers

const movement = [200, 450, -400, 3000, -650, -130, 70, 1300];

console.log(movements.sort()); --> [-130, -400, -650, 1300, 200, 3000, 450, 70]


And if we look at the results above as if they were strings, then the result actually makes sense. So the minus you see always comes first. Then afterwards, you start with the first digit, which starts with 1. Followed by a number that starts with 2, then 3, then 4, and finally 7. So these three are alphabetically ordered if they were strings.


In order to fix this we need to do the following:


// think of a and b as being two consecutive numbers in the array

// ASCENDING ORDER

// return < 0 - A, B (keep order)

// return > 0 - B, A (switch order)

movements.sort(function (a, b) {

	if (a > b) {

		return 1;

	} else if (a < b) {

		return -1;

	}

});


console.log(movements); --> [-650, -400, -130, 70, 200, 450, 1300, 3000]


Now as we see here, the array is now sorted in an ascending order. That is because basically the sort method keeps looping over the array and applying the callback function until everything is in an ascending order according to the rules that we established.


So returning 1 basically means to switch the order.


// DESCENDING ORDER

If you wanted to sort in descending order, you would switch it the other way around.

movements.sort(function (a, b) {

	if (a > b) {

		return -1;

	} else if (a < b) {

		return 1;

	}

});

console.log(movements); --> [3000, 1300, 450, 200, 70, -130, -400, -650]


Now, if you have a mixed array, like with strings and numbers together, then this is not gonna work and it is advised to simply not to use the sort method in these cases anyway.


-----------------------------------------------------------------------------------------------------------------

Applied this knowledge into the Bankist App by adding the sort button functionality. This will allow the user to sort their movements/transactions in descending order.

GitHub Repo: https://github.com/rosajen27/bankist



-----------------------------------------------------------------------------------------------------------------


### Day 52: June 18, 2021

**Today's Progress**: learning how to programmatically create and fill arrays


**Thoughts**: So far when using arrays I have used them like this:


[1, 2, 3, 4, 5, 6, 7]

or

new Array(1, 2, 3, 4, 5, 6, 7)


In these cases, we already have our data, so therefore we could manually create these arrays. However, there is a way to generate arrays programmatically - without having to define all the items manually. There are many situations in which this is necessary and there are also multiple ways of doing it. 


The easiest one is to use the Array() constructor function:

const x = new Array(7);


We might think that this is going to create an array with only one element number seven. But instead it creates a new array with seven empty elements in there and it simply contains nothing.

console.log(x); --> (7) [empty x 7]


The reason for that is this weird behavior of this Array() function which does it so that whenever we only pass in one argument, then it creates a new empty argument with that length.


So if we don't know about this special particularity of the Array() constructor function then this can lead to weird errors.


The only method we can call on this empty array is the fill() method. 


So that's x.fill() and then all we need to do is to pass in a value and it will then fill up the entire array with this specific value. This does actually mutate the underlying array.


x.fill(1);

console.log(x); --> (7) [1, 1, 1, 1, 1, 1, 1]


So besides this value that we want to fill the array with, we can also specify where we want it to start to fill.


x.fill(1, 3);

console.log(x); --> (7) [empty x 3, 1, 1, 1, 1]

--

x.fill(1, 3, 5);

console.log(x); --> (7) [empty x 3, 1, 1, empty x 2]


--


We can also use the fill() method on other arrays. It does not have to be an empty array.


const arr = [1, 2, 3, 4, 5, 6, 7];

arr.fill(23, 2, 6);

console.log(arr); --> [1, 2, 23, 23, 23, 23, 7]


--


What if he wanted to create this arr array programmatically? We could use the Array.from() function.

// Array here is a function, and then on this function object, we call the from() method. We are using it on the Array() contructor.

const y = Array.from({length: 7}, function() {

	return 1;

});

console.log(y); --> (7) [1, 1, 1, 1, 1, 1, 1]

--

const z = Array.from({length: 7}, function(currentElement, i) {

	return i + 1;

});

console.log(z) --> (7) [1, 2, 3, 4, 5, 6, 7]


--

Another example: You can create an array with 100 random dice rolls.


const diceRoll = Array.from({length: 100}, function() {

	return Math.floor(Math.random() * 6 + 1);


});

console.log(diceRoll);


--


Iterables such as Strings, Maps, or Sets can be converted to real arrays using Array.from(). That's also the reason for the name of the function, because we can create arrays from other things.


Another great example of an array-like structure is the result of using querySelectorAll(). Using querySelectorAll() returns a NodeList, which is something like an array, which contains all the selected elements. BUT it is not a real array, and so it doesn't have methods like map() or reduce(), for example. 

So if we actually wanted to use a real array method like that on a NodeList, we would first need to convert the NodeList to an array.


// An example with the Bankist App

labelBalance.addEventListener("click", function () {

  const movementsUI = Array.from(document.querySelectorAll(".movements__value"));


  console.log(movementsUI.map(function (el) {

    return Number(el.textContent.replace('€', ''));


  }));

});



-----------------------------------------------------------------------------------------------------------------


### Day 53: June 19, 2021

**Today's Progress**: Which array method to use?


**Thoughts**: The best way to figure out which method to use in each situation is by starting to ask the question, what do I actually want from this method? In order to help with this decision, we can categorize the methods, and then easily choose between them.


### To mutate original array


***Add to original***
- .push (end)
- .unshift (start)

***Remove from original***
- .pop (end)
- . shift (start)
- .splice (any)

***Others***
- .reverse
- .sort
- .fill


----------


### A new array


***Computed from original***
- .map (loop)

***Filtered using condition***
- .filter

***Portion of original***
- .slice

***Adding original to other***
- .concat

***Flattening the original***
- .flat
- .flatMap


----------


### An array index


***Based on value***
- .indexOf

***Based on test condition***
- .findIndex


----------


### An array element

***Based on test condition***
- .find


----------


### To know if array includes


***Based on value***
- .includes

***Based on test condition***
- .some
- .every


----------


### A new string


***Based on separator string***
- .join


----------


### To transform to value


***Based on accumulator***
- .reduce

(boil down array to a single value of any type: number, string, boolean, or even new array or object)


----------


## To just loop array


***Based on callback***
- .forEach

(does not create a new array, just loops over it)



-----------------------------------------------------------------------------------------------------------------


### Day 54: June 20, 2021

**Today's Progress**: Array Methods Practice


**Thoughts**: 

## Exercise #1: Calculate how much has been deposited in total in the bank.


// map method because we basically want to create a new array out of the accounts array.


const bankDepositSum = accounts.map(function(account) {

	return account.movements.flat();

});

console.log(bankDepositSum); --> (4) [Array(8), Array(8), Array(8), Array(5)]

0: (8) [200, 450, -400, 3000, -650, -130, 70, 1300]

1: (8) [5000, 3400, -150, -790, -3210, -1000, 8500, -30]

2: (8) [200, -200, 340, -300, -20, 50, 400, -460]

3: (5) [430, 1000, 700, 50, 90]


------------------

// Now, how do we get all of these values out of the arrays and into the main arrays? Whenever we have an array of a arrays, how can we basically remove all the values into the parent array?


For that, we can use the flat method.


const bankDepositSum = accounts.flatMap(function(account) {

	return account.movements;

});

console.log(bankDepositSum); --> (29) [200, 450, -400, 3000, -650, -130, 70, 1300, 5000, 3400, -150, -790, -3210, -1000, 8500, -30, 200, -200, 340, -300, -20, 50, 400, -460, 430, 1000, 700, 50, 90]

-----------------------------------------

// Now we filter for the deposits (positive values) and all them all together


const bankDepositSum = accounts.flatMap(function(account) {

	return account.movements;

}).filter(function(movement) {

	return movement > 0;

}).reduce(function(sum, cur) {

	return sum + cur

}, 0);

console.log(bankDepositSum); --> 25180


-----------------------------------------


## Exercise 2: Count how many deposits there have been in the bank with at least $1,000

// using filter

const numDeposits1000 = accounts.flatMap(function(account) {

	return account.movements;

}).filter(function(movement) {

	return movement >= 1000;

}).length;


console.log(numDeposits1000); --> 6



// using reduce

const numDeposits1000 = accounts.flatMap(function(account) {

	return account.movements;

}).reduce(function(count, cur) {
	return count + cur >= 1000 ? count + 1 : count;
}, 0);


console.log(numDeposits1000); --> 6



-----------------------------------------


### Day 55: June 21, 2021

**Today's Progress**: Array Methods Practice Part 2


**Thoughts**: 

## Exercise #3: Create an object which contains the sum of the deposits and of the withdrawals.

We already know that reduce boils down an array to just one value. So that value might be an object. It could even be a new array as well. In fact, we could use reduce to replace many of the other methods that we have. 


const sums = accounts.flatMap(function (account) {

	return account.movements;

}).reduce(function (sums, cur) {

	cur > 0 ? sums.deposits += cur : sums.withdrawals += cur;

	return sums;

}, {deposits: 0, withdrawals: 0});


console.log(sums); --> {deposits: 25180, withdrawals: -7340}

-----------------------------------------

We can also destructure this object immediately by...


const {deposits, withdrawals} = accounts.flatMap(function (account) {

	return account.movements;

}).reduce(function (sums, cur) {

	cur > 0 ? sums.deposits += cur : sums.withdrawals += cur;

	// another way -- sums[cur > 0 ? 'deposits' : 'withdrawals'] += cur;

	return sums;

}, {deposits: 0, withdrawals: 0});


console.log(deposits, withdrawals); --> {25180 -7340}

-----------------------------------------


## Exercise #3: Create a function to convert any string to a title case (all the words in a sentence are capitalized - with some exceptions)

const convertTitleCase = function (title) {

  const exceptions = ['a', 'an', 'and', 'the', 'but', 'or', 'on', 'in', 'with'];

 
  const titleCase = title

    .toLowerCase()

    .split(' ')

    .map(function (word) {

      return exceptions.includes(word)

        ? word

        : word[0].toUpperCase() + word.slice(1);

    })

    .join(' ');

 
  return titleCase;

};


console.log(convertTitleCase("this is a NICE string"));



** Note: Here we used the exceptions array to exclude words in exceptions array from being capitalized. Excluding kind of sounds like filtering, but that's not what we want here because we still want to keep an array of the same length. We just don't want to apply this to all the words. So we will do exceptions and then we are going to check if the current word is included in that array (includes() method). So with the includes() method, we are checking for that word. And then as you notice, we'll return a boolean -- so true, false. Then we can use that boolean to basically ask if the word is an exception or not. So if the word is included in the exceptions array, then we want to simply return that word (as is in lowercase). And only otherwise we want to then return the capitalized version.



-----------------------------------------


### Day 56: June 22, 2021

**Today's Progress**: Coding challenge provided by Jonas Schmedtmann's JavaScript Course


**Thoughts**: Coding Challenge:

Julia and Kate are still studying dogs, and this time they are studying if dogs are eating too much or too little. Eating too much means the dog's current food portion is larger than the recommended portion, and eating too little is the opposite. Eating an okay amount means the dog's current food portion is within a range 10% above and 10% below the recommended portion.


const dogs = [

  { weight: 22, curFood: 250, owners: ['Alice', 'Bob'] },

  { weight: 8, curFood: 200, owners: ['Matilda'] },

  { weight: 13, curFood: 275, owners: ['Sarah', 'John'] },

  { weight: 32, curFood: 340, owners: ['Michael'] },

];



// v Loop over the 'dogs' array containing dog objects, and for each dog, calculate the recommended food portion and add it to the object as a new property.


const recommendedFood = function (dogs) {

  dogs.recFood = Math.trunc(dogs.weight ** 0.75 * 28);

};

dogs.forEach(recommendedFood);

console.log(dogs);


// x Find Sarah's dog and log to the console whether it's eating too much or too little.

const sarahsDog = dogs.find(function (dog) {

  return dog.owners.includes("Sarah");

});

console.log(sarahsDog);

console.log(`Sarah's dog is eating too ${sarahsDog.curFood > sarahsDog.recFood ? "much" : "little"} food.`);


// vx Create an array containing all owners of dogs who eat too much and an array with all owners of dogs who eat too little

const ownersEatTooMuch = dogs.filter(function (dog) {

  return dog.curFood > dog.recFood

}).flatMap(function (dog) {

  return dog.owners

});

console.log(ownersEatTooMuch);


const ownersEatTooLittle = dogs.filter(function (dog) {

  return dog.curFood < dog.recFood

}).flatMap(function (dog) {

  return dog.owners

});

console.log(ownersEatTooLittle);


// v Log a string to the console for each array created

console.log(`${ownersEatTooMuch.join(" and ")}'s dogs eat too much!`);

console.log(`${ownersEatTooLittle.join(" and ")}'s dogs eat too little!`);


// vx Log to the console whether there is any dog eating exactly the amount of food that is recommended

const exactFood = dogs.some(function (dog) {

  return dog.curFood === dog.recFood;

});

console.log(exactFood);


// v Log to the console whether there is any dog eating an okay amount of food

const okayFood = dogs.some(function (dog) {

  return dog.curFood > (dog.recFood * 0.90) && dog.curFood < (dog.recFood * 1.10);

});

console.log(okayFood);


// v Create an array containing the dogs that are eating an okay amount of food

const okayFoodArr = dogs.filter(function (dog) {

  return dog.curFood > (dog.recFood * 0.90) && dog.curFood < (dog.recFood * 1.10);

});

console.log(okayFoodArr);


// vx Create a shallow copy of the 'dogs' array and sort it by recommended food portion in an ascending order

const copy = dogs.slice().sort(function (a, b) {

  return a.recFood - b.recFood;

});

console.log(copy);


(Note: Personal codes for future reference. v = completely solved on own | x = did not solve on own | vx = partially solved on own or hints helped)



-----------------------------------------



### Day 57: June 23, 2021

**Today's Progress**: Repeating yesterday's Coding Challenge provided by Jonas Schmedtmann's JavaScript Course


**Thoughts**: Since there were a few steps in the coding challenge that I could not solve on my own, I decided to repeat solving this challenge today in order to solidify what I have learned before moving on to the next topic. Repetition has proven to be helpful in understanding when and why certain methods should be used.


I was able to answer steps 1-4 and 7-8 independently. With step 5 & 6, I tend to forget that the some() method exists. I first attempted to solve by using the filter() and reduce() methods, but would get opposite result.


The reduce() method did not work in this situation because this method is used to boil ("reduce") down all of the elements of the original array into one single value.


The filter() method did not work in this situation because this method is used to filter for elements in the original array, which satisfies a certain condition.


The some() method works because if there is any value for which this condition is true, then the some method will return true.

const dogs = [

  { weight: 22, curFood: 250, owners: ['Alice', 'Bob'] },

  { weight: 8, curFood: 200, owners: ['Matilda'] },

  { weight: 13, curFood: 275, owners: ['Sarah', 'John'] },

  { weight: 32, curFood: 340, owners: ['Michael'] },

];

// 1. Loop over the array containing dog objects, and for each dog, calculate the recommended food portion and add it to the object as a new property.

// Formula: recommendedFood = weight ** 0.75 * 28

const recommendedFood = function (dog) {

  dog.recFood = Math.trunc(dog.weight ** 0.75 * 28);

};

dogs.forEach(recommendedFood);

console.log(dogs);



// 2. Find Sarah's dog and log to the console whether it's eating too much or too little

const sarahsDog = dogs.find(function (dog) {

  return dog.owners.includes("Sarah");

});


console.log(sarahsDog);

console.log(`Sarah's dog is eating ${sarahsDog.curFood > sarahsDog.recFood ? "too much" : "too little"} food.`);



// 3. Create an array containing all the owners of dogs who eat too much and an array with all owners of dogs who eat 
too little

const ownersEatTooMuch = dogs.filter(function (dog) {


  return dog.curFood > dog.recFood;

}).flatMap(function (dog) {

  return dog.owners;

});

console.log(ownersEatTooMuch);



const ownersEatTooLittle = dogs.filter(function (dog) {

  return dog.curFood < dog.recFood;

}).flatMap(function (dog) {

  return dog.owners;

});

console.log(ownersEatTooLittle);



// 4. Log a string to the console for each array created

console.log(`${ownersEatTooMuch.join(" and ")}'s dogs each too much!`);

console.log(`${ownersEatTooLittle.join(" and ")}'s dogs each too little!`);



// 5. Log to the console whether there is any dog eating exact amount of recommended food

const exactAmountFood = dogs.some(function (dog) {

  return dog.curFood === dog.recFood;

});

console.log(exactAmountFood);



// 6. Log to the console whether there is any dog eating an okay amount of food

// Formula: currentFood > (recommendedFood * 0.90) && currentFood < (recommendedFood * 1.10)

const okayAmountFood = dogs.some(function (dog) {

  return dog.curFood > (dog.recFood * 0.90) && dog.curFood < (dog.recFood * 1.10);

});

console.log(okayAmountFood);



// 7. Create an array containing the dogs that are eating an ok amount of food

const okayAmountFoodArr = dogs.filter(function (dog) {

  return dog.curFood > (dog.recFood * 0.90) && dog.curFood < (dog.recFood * 1.10);

});

console.log(okayAmountFoodArr);



// 8. Create a shallow copy of the dogs array and sort it by recommended food portion in ascending order

const dogsCopy = dogs.slice().sort(function (a, b) {

  return a.recFood - b.recFood;

});

console.log(dogsCopy);



-----------------------------------------



### Day 58: June 24, 2021

**Today's Progress**: Converting & Checking Numbers


**Thoughts**: In JavaScript, all numbers are presented internally as floating point numbers. So basically, always as decimals, no matter if we actually write them as integers or as decimals.


console.log(23 === 23.0); --> true


23 is, in fact, the same as 23.0. And that's the reason why we only have one data type for all numbers. Also, numbers are represented internally in a 64 base 2 format. So that means that numbers are always stored in a binary format -- they're only composed of zeros and ones.


Now, in this binary form, it is very hard to represent some fractions that are very easy to represent in the base 10 system that we are used to. Base 10 is basically the numbers from zero to nine, while binary is base 2 and so that's the numbers zero and one.


There are certain numbers that are very difficult to represent in base 2. One example of that is the fraction 0.1. And that then results in very weird results like this.


console.log(0.1 + 0.2); --> 0.30000000000000004


This is kind of a running joke in JavaScript because this result should, of course, be 0.3 But JavaScript simply has no better way of representing this number.


So in base 10, 1/10 is simply 0.1. And so that's very easy to represent. But, for example, if we were trying to do 3/10, then that is also impossible to represent for us, right? It would be this number here (3.33333333333 etc) and three until infinity, okay?


And so in binary, the same thing happens with 0.1. We get basically an infinite fraction and that then results in a weird result like this one (0.30000000000000004).

--

- Conversion: To convert a string into a number you can do either of the following:

console.log(Number(23)); or simply use the plus operator console.log(+23);


- Parsing: You can also parse a number from a string:

console.log(Number.parseInt("30px")); --> 30


console.log(Number.parseInt("e30px")); --> NaN


console.log(Number.parseInt("2.5rem")); --> 2.5


console.log(Number.parseFloat("2.5rem")); --> 2


Note: in order for this to work, the string has to start with a number. The parseInt function actually accepts a second argument, which is the so-called regex. And the regex is the base of the numeral system that we are using. So here we are simply using base 10 numbers. So numbers from zero to nine. And most of the time, we are doing that and so we should always pass in the number 10 here. So that can avoid some bugs in some situations.


The parseFloat function should be your go-to whenever you need to read a value out of a string -- for example, coming from CSS.


- isNAN: check if value is not a number


console.log(Number.isNaN(20)); --> false

console.log(Number.isNaN("20")); --> false

console.log(Number.isNaN(+"20X")); --> true

console.log(Number.isNaN(23/0)); --> false


In summary, the Number.isNan()-method only returns true if the variable supplied as an argument is of the value NaN, and of the type Number.


- isFinite: this methos is better when trying to check if a value is a number or not


console.log(Number.isFinite(20)); --> true

console.log(Number.isFinite("20")); --> false

console.log(Number.isFinite(+"20X")); --> false

console.log(Number.isFinite(23/0)); --> false



-----------------------------------------



### Day 59: June 25, 2021

**Today's Progress**: Math + Rounding


**Thoughts**: 



- Square Root

console.log(Math.sqrt(25)); --> 5

console.log(25 ** (1/2)); --> 5



- Maximum value

console.log(Math.max(5, 18, 23, 11, 2)); --> 23

console.log(Math.max(5, 18, "23", 11, 2)); --> 23

console.log(Math.max(5, 18, "23px", 11, 2)); --> NaN (Parsing does not work in this case)



- Minimum Value

console.log(Math.min(5, 18, 23, 11, 2)); --> 2



- Constants

console.log(Math.PI); --> 3.141592653589793

console.log(Math.PI * Number.parseFloat("10px") ** 2); // Calculating area of a circle with radius of 10 --> 314.
1592653589793

console.log(Math.trunc(Math.random() * 6) + 1); // Generate a random number between 1 - 6



// will return a random number between min & max

const randomInt = function(min, max) {

	return Math.trunc(Math.random() * (max - min) + 1) + min;

};

console.log(randomInt(1, 20));



- Rounding integers

// Remove digits after the decimal point

console.log(Math.trunc(23.3)); --> 23



// Rounded to nearest whole number

console.log(Math.round(23.3)); --> 23

console.log(Math.round(23.9)); --> 24




// Rounded UP

console.log(Math.ceil(23.3)); --> 24

console.log(Math.ceil(23.9)); --> 24 



// Rounded DOWN

console.log(Math.floor(23.3)); --> 23

console.log(Math.floor(23.9)); --> 23 



- Rounding decimals

console.log(2.7).toFixed(0); --> 3 // will return as a string, not a number

console.log(2.7).toFixed(3); --> 2.700

console.log(2.345).toFixed(2); --> 2.35

console.log(+2.345).toFixed(2); // plus sign will convert a string to a number

----------

Bankist App Updates

GitHub Repo: https://github.com/rosajen27/bankist


- Math.floor() method implemented when user requests loan

- .toFixed() method implemented so that all dollar amounts are shown as $x.xx

-----------------------------------------



### Day 60: June 26, 2021

**Today's Progress**: The Remainder Operator

**Thoughts**: The remainder operator returns the remainder of a division. 


console.log(5 % 2); --> 1 Remainder

console.log(5 / 2); --> 2.5 // Because 5 = 2 * 2 + 1


console.log(8 % 3); --> 2 Remainder

console.log(8 / 3); --> 2.6666666 // Because 8 = 2 * 3 + 2


One thing that is many times used for programming, is to check whether a certain number is even or odd. A number is even when it is divisible by two (meaning -- if we divide it by two, the remainder is zero).

console.log(6 % 2); --> 0 


const isEven = function(n) {

	return n % 2 === 0;

}


console.log(isEven(8)); --> true

console.log(isEven(3)); --> false


Real World Example: If we wanted to change the background color of every other transaction in Bankist App:



labelBalance.addEventListener("click", function() {

	[...document.querySelectorAll(".movements__row")].forEach(function(row, i) {

		if (i % 2 === 0) row.style.backgroundColor = "orangered";

	});

});



-----------------------------------------



### Day 61: June 27, 2021

**Today's Progress**: BigInt


**Thoughts**: As previously learned, numbers are represented internally as 64 bits. That means that there are exactly 64 ones or zeros to represent any given number. Now of these 64 bits, only 53 are used to actually store the digits themselves. The rest are for storingg the position of the decimal point and the sign. 


If there are only 53 bits to store the number, that means that there is a limit of how big numbers can be, and we can calculate that number.


console.log(2 ** 53 - 1); --> 9007199254740991 // This is essentially the biggest number that JavaScript can safely represent


console.log(Number.MAX_SAFE_INTEGER); --> 9007199254740991 // This number is so important that it's even stored into the number namespace MAX SAFE INTEGER. So any integer that is larger than this, is not safe and that means it cannot be represented accurately. So if we do calculations with numbers that are bigger than this, then we might lose precision.


This can be a problem sometimes because in some situations, we might need really big numbers. For example - for database IDs or when interacting with real 60 bit numbers. 


However, since ES2020 - a new primivite was added, which is called BigInt (big integer). It can be used to store numbers as large as we want. 


console.log(123456789123456789123456789); --> 1.2345678912345679e+26

console.log(123456789123456789123456789n); --> 123456789123456789123456789n // Including the n at the end, transforms a regular number into a BigInt number.


All usual operators still work the same. However, what is not possible is mixing BigInts with regular numbers - you would have to fist use the BigInt constructor.


const huge = 123456789123456789123456789n;

const num = 23;

console.log(huge * BigInt(num));



-----------------------------------------



### Day 62: July 1, 2021

**Today's Progress**: (Returned from mini vacation :) ) -- Creating Dates


**Thoughts**:

// Create a date

const now = new Date();

console.log(now); --> // *displays current date and time at this very moment*


// Parse date from a date string

console.log(new Date("December 24, 2021")); --> Fri Dec 24 2021 00:00:00 GMT-0500 (Eastern Standard Time)


We can also pass in year, month, day, hour, minute, and second into the constructor. Important Note: The MONTH is ZERO BASED (0 = January).


console.log(new Date(2037, 10, 19, 15, 23, 5)); --> Thu Nov 19 2037 15:23:00 GMT-0500 (Eastern Standard Time)


// Working with dates

const future = new Date(2037, 10, 19, 15, 23);

console.log(future); --> Thu Nov 19 2037 15:23:00 GMT-0500 (Eastern Standard Time)


console.log(future.getFullYear()); --> 2037

console.log(future.getMonth()); --> 10 *remember this is zero based*

console.log(future.getDate()); --> 19

console.log(future.getDay()); --> 4 // Thursday

console.log(future.getHours()); --> 15

console.log(future.getMinutes()); --> 23

console.log(future.getSeconds()); --> 0

console.log(future.getISOString()); --> 2037-11-19T15:23:00.000Z


console.log(future.getTime()); --> 2142256980000 *amount of milliseconds that have passed since Jan 1, 1970*

console.log(new Date(2142256980000)); Thu Nov 19 2037 15:23:00 GMT-0500 (Eastern Standard Time)


// Setting a date

future.setFullYear(2040);

console.log(future); --> Mon Nov 19 2040 15:23:00 GMT-0500 (Eastern Standard Time)


You can also use this to set month, date, etc.


----------

Bankist App Updates

GitHub Repo: https://github.com/rosajen27/bankist


- Display Current Date under 'Current Balance' heading

- For each movement/transaction - display date

- Added dates to loans and transfers movements/transactions




-----------------------------------------



### Day 63: July 2, 2021

**Today's Progress**: Operations with dates


**Thoughts**: 

// Calculations with dates

const future = new Date(2037, 10, 19, 15, 23);

console.log(Number(future)); --> 2142274980000 // time stamp in milliseconds

console.log(+future); --> 2142274980000



const calcDaysPassed = function(date1, date2) {

	return date2 - date1;


}

const days1 = calcDaysPassed(new Date(2037, 3, 14), new Date(2037, 3, 24));

console.log(days1); --> 864000000





const calcDaysPassedConverted = function(date1, date2) {

	// convert milliseconds - 

	// * 1000 to convert milliseconds to seconds

	// * 60 to convert seconds to minutes

	// * 60 to convert minutes to hours

	// * 24 to convert hours to days

	return date2 - date1 / (1000 * 60 * 60 * 24);

}



const days2 = calcDaysPassedConverted(new Date(2037, 3, 14), new Date(2037, 3, 24));

console.log(days2); --> 10 // days

-----------------------------

We can use this function to format and display or dates in a different way within the Bankist application.
For example, if one movement happened today, then instead of the current date, it can display "today", then if it happened yesterday, it can display "yesterday". And then if it happened two days ago or five days ago, instead of the date.


This has been featured on many social media platforms. For example, if you post something on Facebook, and if you didn't watch it the next day, it will say that you posted it yesterday, it's not going to display the exact date.


const calcDaysPassed = function(date1, date2) {

	return Math.round(Math.abs(date2 - date1 / (1000 * 60 * 60 * 24)));

}


const daysPassed = calcDaysPassed(new Date(), date) {

	if (daysPassed === 0) {

		return "Today";

	} else if (daysPassed === 1) {

		return "Yesterday";

	} else if (daysPassed <= 7) {

		return `${daysPassed} days ago`

	} else {

		    const day = `${now.getDate()}`.padStart(2, 0);

    		const month = `${now.getMonth() + 1}`.padStart(2, 0); // because it is zero based

    		const year = now.getFullYear();

			return `${day}/${month}/${year}`;

	}

};


*Note: I decided not to apply this to the application* 





-----------------------------------------



### Day 64: July 3, 2021

**Today's Progress**: Internationalizing Dates


**Thoughts**: 

Instead of coding dates like this:

    const now = new Date();

    const day = `${now.getDate()}`.padStart(2, 0);

    const month = `${now.getMonth() + 1}`.padStart(2, 0); // because it is zero based

    const year = now.getFullYear();

    const hour = `${now.getHours()}`.padStart(2, 0);

    const min = `${now.getMinutes()}`.padStart(2, 0);

    labelDate.textContent = `${month}/${day}/${year}, ${hour}:${min}`;



You can use the Internationalization API:

const now = new Date();

labelDate.textContent = new Intl.DateTimeFormat("en-US").format(now);


ISO Language Code Table: http://www.lingoes.net/en/translator/langcode.htm

-----------------------------------------
You can also display time by providing an options object to the function:


const now = new Date();

const options = {

	hour: "numeric",

	minute: "numeric",

	day: "numeric",

	month: "numeric",

	year: "numeric",

	weekday: "long"
}

labelDate.textContent = new Intl.DateTimeFormat("en-US", options).format(now);

*Other options include "long", "2-digit", "short", "narrow"*

-----------------------------------------

In many situations, it actually makes more sense to not define locale manually, but to simply get it from the user's browser.

const now = new Date();

const locale = navigator.language;

const options = {

	hour: "numeric",

	minute: "numeric",

	day: "numeric",

	month: "numeric",

	year: "numeric",

	weekday: "long"
}

labelDate.textContent = new Intl.DateTimeFormat(locale, options).format(now);


-----------------------------------------



### Day 65: July 4, 2021

**Today's Progress**: Internationalizing Numbers


**Thoughts**: 

const num = 3884764.23;



console.log("US: ", new Intl.NumberFormat("en-US").format(num));

console.log("Germany: ", new Intl.NumberFormat("de-DE").format(num));

console.log("Syria: ", new Intl.NumberFormat("ar-SY").format(num));



--> 

US:  3,884,764.23

Germany:  3.884.764,23

Syria:  ٣٬٨٨٤٬٧٦٤٫٢٣



-----------------------------------------

const num = 3884764.23;

const options = {

	style: "unit",

	unit: "mile-per-hour",

};

console.log("US: ", new Intl.NumberFormat("en-US", options).format(num));

console.log("Germany: ", new Intl.NumberFormat("de-DE", options).format(num));

console.log("Syria: ", new Intl.NumberFormat("ar-SY", options).format(num));

console.log(navigator.language, new Intl.NumberFormat(navigator.language, options).format(num));



-->

US:  3,884,764.23 mph

Germany:  3.884.764,23 mi/h

Syria:  ٣٬٨٨٤٬٧٦٤٫٢٣ ميل/س

en-US 3,884,764.23 mph

-----------------------------------------

Some other examples include:


const options = {

	style: "unit",

	unit: "celsius"

};



const options = {

	style: "percent",

};



const options = {

	style: "currency",

	currency: "EUR"

};

*Note: We do infact have to label the currency, as it is not determined by the locale*

-----------------------------------------



### Day 66: July 5, 2021

**Today's Progress**: Timers (setTimeout & setInterval)


**Thoughts**: The setTimeout() timer runs just once, after a defined time, while the setInterval() timer keeps running forever, until we stop it.

We can use setTimeout to execute some code at some point in the future.


setTimeout(function() {

	console.log("Here is your pizza 🍕"); 

}, 3000);


--> // after 3 seconds, the console will log the message above


Any argument that you pass after the delay, will be arguments to the function.


setTimeout(function(ing1, ing2) {

	console.log(`Here is your pizza 🍕 with ${ing1} and ${ing2}`); 

}, 3000, "olives", "spinach");



--> // after 3 seconds, the console will log the message above



-----------------------------------------



We can also cancel the timer, at least until before the delay has actually passed. 



const ingredients = ["olives", "spinach"];



const pizzaTimer = setTimeout(function(ing1, ing2) {

	console.log(`Here is your pizza 🍕 with ${ing1} and ${ing2}`); 

}, 3000, ...ingredients);

console.log("Waiting...");



if (ingredients.includes("spinach")) clearTimeout(pizzaTimer);


-----------------------------------------
// setInterval

setInterval(function() {
	const now = new Date();
	console.log(now);
}, 1000);

--> // will print the date every second on the console

-----------------------------------------



### Day 67: July 6, 2021

**Today's Progress**: Implementing a countdown timer & completion of Bankist App


**Thoughts**: GitHub Repo: https://github.com/rosajen27/bankist

For security reasons, real bank applications will log users out after some inactive time. A 5 minute countdown timer was implemented, which is displayed in the UI. User will be logged out after 5 minutes of inactivity. With this addition, the Bankist Application is now complete.



-----------------------------------------



### Day 68: July 7, 2021

**Today's Progress**: DOM


**Thoughts**: The DOM is basically the interface between all the JS code and the browser, or more specifically HTML documents that are rendered in and by the browser.


- The DOM allows us to make JS interact with the browser
- We can write JS to create, modify, and delete HTML elements; set styles, classes and attributes; and listen and respond to events
- DOM tree is generated from an HTML document, which we can then interact with
- DOM is a very complex API (application programming interface) that contains lots of methods and properties to interact with the DOM tree [querySelector(), addEventListener(), createElement(), innerHTML(), textContent, children, etc]


How to DOM API is organized behind the scenes:

- Every single node in the DOM tree, is of the type Node
- Each Node is represented in JS by an object. This object gets special node methods and properties such as textContent, child nodes, parent nodes, clone nodes, and many others
- There are different kinds of Nodes that can be represented as the element, text, comment, or document type
- So whenever there is text inside any element, we already know that it gets its own node. That node will be of the type text
- The same actually happens for HTML comments
- For the element itself, there is the element type of node. And this type of node gives each HTML acess to a ton of useful properties such as innerHTML, classList, children or parent elements. There are also many useful methods like append, remove, insertAdjacentHTML, querySelector, etc
- Each element will be represented internally as an object
- The element type has internally an HTML element, child type. That element type itself has exactly one child type for each HTML element that exists in HTML
- We have a special type for buttons, images, links, etc. This is important because each of these HTML elements can have different unique properties (For example, an image has a source attribute in HTML, which no other element has)
- Inheritance of Methods and Properties: Inheritance means that all the child types will also get access to the methods and properties of all their parent node types (for ecample, an HTML element will get access to everything from the element type, like innerHTMl, or classList)
- Document: Document is just another type of Node, so it contains important methods such as querySelector, createElement, and getElementbyID



-----------------------------------------



### Day 69: July 8, 2021

**Today's Progress**: Selecting, Creating, and Deleting Elements (review)


**Thoughts**: SELECTING - We have a special way of selecting the entire document of any webpage(document), and that is documentElement. We can also easily select the head and body.

console.log(document.documentElement);

console.log(document.head);

console.log(document.body);


document.querySelector(".header"); --> // will return the first element that matches the selector.

const allSections = document.querySelectorAll(".section"); --> // will return all elements that matches the selector.

console.log(allSections); --> // will return a node list that contains all of the elements that are selected by this selector

-----

document.getElementByID("section--1");

const allButtons = document.getElementsByTagName("button");

console.log(allButtons); --> // returns all of the buttons on our webpage. This method actually returns an HTML collection, which is different from a Node list. An HTML collection is actually a so called live collection, which means if the DOM changes, then this collection is also immediately updated automatically. The same does not happen with a Node list - it does not update itself.


document.getElementsByClassName("btn"); --> // will also return a live HTML collection

--------------------------------------------------------

CREATING & INSERTING - We can create HTML elements using insertAdjacentHTML or createElement. If we want it to appear onto the page, then we have to manually insert it.

const header = document.querySelector(".header");

const message = document.createElement("div");

message.classList.add("cookie-message");

message.innerHTML = "We use cookies for improved functionality and analytics. <button class='btn btn--close--cookie'>Got it!</button>";

header.append(message);

// two other methods include .before() and .after() - which will appear before or after the element as a sibling

--------------------------------------------------------

DELETE -

document.querySelector(".btn--close--cookie").addEventListener("click", function() {
	message.remove();
});


-----------------------------------------



### Day 70: July 9, 2021

**Today's Progress**: Styles, Attributes, Classes (review)


**Thoughts**: 

// STYLES

message.style.backgroundColor = "#37383d";

message.style.width = "120%";



console.log(message.style.height); --> // returns nothing because using the style property like this here only works for inline styles that we set ourselves also using this style property


console.log(message.style.backgroundColor); --> // this will return the background color because it is an inline style, so a style that we set manually ourselves


console.log(message.style.color); --> // returns nothing because we cannot get a style that is hidden inside of a class or that does not exist

----------

console.log(getComputerStyle(message)); --> // returns large object with all styles

console.log(getComputedStyle(message).color);

console.log(getComputedStyle(message).height);

// COMPUTED, which means that it's the real style as it appears on the page - even if we do not declare it in our CSS

// since getComputerStyle returns a string, we must parse the digits and turn it into a number before we can add a number to it.

message.style.height = Number.parseFloat(getComputedStyle(message).height, 10) + 30 + "px";

----------

// CSS Variables (Custom Properties)

document.documentElement.style.setProperty("--color-primary", "orangered"); --> // everywhere in our style where we used the primary color, it is now orange red

----------

// ATTRIBUTES

Examples of attributes include source, alt, class, IDs, etc. So in JS ofcourse we can access and change these different attributes. 


const logo = document.querySelector(".nav__logo");

console.log(logo.alt); --> // will display alternative text

console.log(logo.src); --> // will display absolute URL -- the same is true for href links

console.log(logo.className); --> // will display class name

console.log(logo.designer); --> // undefined because it is a NON STANDARD

console.log(logo.getAttribute("designer")); --> Jonas


So if we specify them in HTML, then JS will automatically create these properties on the object, but if we add some other property that is not a standard then JS will not create a property on the object (in order to be able to do this you must use getAttribute).


Just as we can read these attributes, we can also define them.


logo.alt = "Beautiful minimalist logo";

logo.setAttribute("company", "Bankist"); 

----------

// Data Attributes

console.log(logo.dataset.versionNumber); --> // So data, and data attributes are a special kind of attributes that start with the words data. Often used when working with the UI and especially when data needs to be stored in the UI (in the HTML code)


----------

// CLASSES

logo.classList.add();
logo.classList.remove();
logo.classList.toggle();
logo.classList.contains();


-----------------------------------------



### Day 71: July 10, 2021

**Today's Progress**: Smooth scrolling with JavaScript


**Thoughts**: *The simplest way to implement smooth scroll would be through css, however this is an alternative way of doing it with JavaScript*

html {

scroll-behavior: smooth;

}

----------

// Smooth Scrolling with JavaScript (Manually)


// the name of the button

const btnScrollTo = document.querySelector(".btn--scroll-to");


// the name of the section we want to scroll to

const section1 = document.querySelector("#section--1");


// scroll event listener

btnScrollTo.addEventListener("click", function(e) {
	
	// get the coordinates of the element that we want to scroll to
  	
	const s1coords = section1.getBoundingClientRect();
	

	// returns a DOM rectangle, but not the best element to understand this

  	console.log(s1coords);


	// returns rectangle for the button that was clicked
	
	// x: the distance between the border OF THE VISIBLE VIEWPORT
	
	// y: the distance from the top OF THE VISIBLE VIEWPORT
	
	// width and height of button
	
	// top: is similar to y, but it isn't always - because when we scroll, x and y actually change*

  	console.log(e.target.getBoundingClientRect());


  	// returns current scroll position, relative to the top and border of the page
	
	console.log("Current Scroll Positions(X/Y)", window.pageXOffset, window.pageYOffset);
  	

	// returns height and width of viewport

	console.log("height/width of the visible viewport", document.documentElement.clientHeight, document.documentElement.clientWidth);


  	// Scrolling

  	// The purpose of getting these coordinates is to then tell JS where to scroll to
	  
	window.scrollTo({
		
		// add current scroll position + top value
		// this will allow us to determine the position of section we are scrolling to, not relative to the VIEWPORT, but instead to the TOP OF THE PAGE
		
		top: s1coords.top + window.pageYOffset,


		// add current scroll position + border value
		
		left: s1coords.left + window.pageXOffset, 


		behavior: "smooth",

	});


});

-------------

// Modern Method of Smooth Scrolling- only words in modern browsers

btnScrollTo.addEventListener("click", function (e) {

  section1.scrollIntoView({ behavior: "smooth" });

});


----------

Implemented Smooth Scrolling on to my new project, Bankist Ad -- a marketing website for previously completed Bankist App.

GitHub Repo: https://github.com/rosajen27/bankist-ad



-----------------------------------------



### Day 72: July 11, 2021

**Today's Progress**: Types of Events and Event Handlers


**Thoughts**: An event is basically a signal that is generated by a certain DOM Node and a signal means that something has happened. For example, a click somewhere or the moust moving, or the user triggering full screen mode, and really anything of importance that happens on our webpage, generates an event.


We can then listen for these events in our code using Event Listeners, so that we can then handle them, if we'd like. But no matter if we handle a certain event or not (for example, a click), that event will always happen when a user clicks regardless if we're actually listening for it or not.


// Mouse enter - similar to the hover effect in CSS. It fires whenever a mouse enters a certain element

const h1 = document.querySelector("h1");

h1.addEventListener("mouseenter", function(e) {

  alert("addEventListener: You are reading the heading!");

});

----------

// Using Add Event Listener

- Using addEventListener allows us to add multiple event listeners to the same event
- We can also remove an event handler in case we don't need it anymore. This makes it so that we can only listen to the event once


const h1 = document.querySelector("h1");

const alertH1 = function (e) {

  alert("addEventListener: You are reading the heading!");



  h1.removeEventListener("mouseenter", alertH1);

}


h1.addEventListener("mouseenter", alertH1);

----------

- You can also remove it after a certain time has passed:

setTimeout(() => h1.removeEventListener("mouseenter", alertH1), 3000);

----------

// a second way of attaching an eventlistener to an element (the "old school way")

h1.onmouseenter = function(e) {

  alert("addEventListener: You are reading the heading!");

};

----------

// a third way of attaching an event listener to an element (using an HTML attribute -- should NOT be used)

<h1 onclick="alert('HTML alert!')">Header</h1>



-----------------------------------------



### Day 73: July 12, 2021

**Today's Progress**: Event Propagation: Bubbling & Capturing


**Thoughts**: Events propagate (bubble and capture) -- meaning its events transmit from one place to another


<html>

<head>

<title>Title</title>

</head>

<body>

<section>

<p>A paragraph with a <a>link</a></p>

</section>

</body>


DOM Tree: Document --> Element HTML --> Element BODY --> Element SECTION --> Element P --> Element A


Let's say that a click happens on the link. The DOM would generate a click event right away. However, this event is NOT generated at the target element (the element where the event happened ie. the click on the anchor element). Instead, the event is actually generated at the root of the document, so at the very top of the DOM tree.


1. From there, the so-called CAPTURING PHASE happens, where the event then travels all the way down, from the document root to the target element. As the event travels down the tree, it will pass through EVERY single parent element of the target element, until it finally reaches its target.


2. As soon as the event reaches the target, the TARGET PHASE begins -- Where events can be handled right at the target (such as with Event Listeners). Event Listeners wait for a certain event to happen on a certain element. As soon as the event occurs, it runs the attached callback function.


3. After reaching the target, the event then actually travels all the way up to the document route again, in the so-called BUBBLING PHASE. So we say that events bubble up, from the target to the document root. Just like the capturing phase, the event passes through all its parents element (just the parents -- not through any sibling elements). 


Importance: It is as if each event happened in each of the parent elements. So again, as the event bubbles through a parent element, it's as if the event had happened right in that very element. What this means if that if we attach the same event listener, for example, to the section element, then we would get the exact same alert window for the section element as well. So we would have handled the same exact event twice -- once at its targer, and once at one of its parent element. This behavior will allow us to implement powerful patterns. 


By default, events can only be handled in the target, and in the bubbling phase. However, we can set up event listeners in a way that they listen to events in the capturing phase instead. Most elements capture and bubble, but not all types of events have a capturing and bubbling phase. Some of them are created right on the target element, so we can only handle them there.



-----------------------------------------



### Day 74: July 13, 2021

**Today's Progress**: Event Propagation in practice


**Thoughts**:


const randomInt = (min, max) => Math.floor(Math.random() * (max - min + 1) + min);


const randomColor = () => `rgb(${randomInt(0, 255)}, ${randomInt(0, 255)}, ${randomInt(0, 255)})`;


document.querySelector(".nav__link").addEventListener("click", function (e) {

	this.style.backgroundColor = randomColor();

	console.log("LINK", e.target, e.currentTarget);

});


document.querySelector(".nav__links").addEventListener("click", function (e) {

	this.style.backgroundColor = randomColor();

	console.log("CONTAINER", e.target, e.currentTarget);

});


document.querySelector(".nav").addEventListener("click", function (e) {

	this.style.backgroundColor = randomColor();

	console.log("NAV", e.target, e.currentTarget);

});


*Remember that in an event handler, the this keyword points always to the element on which that event handler is 
attached -- in this case it is going to be document.querySelector(".nav__link")*


In this exercise, the click event was handled in all three elements, which have a click event handler. 


The event actually happens at the document root and from there it then travels down to the target element -- in this 
case that is the clicked link. And then from there, it bubbles up. Bubbling up means that basically it's as if the 
event had also happened in all of the parent elements. 


e.target - The target is always the same in all three handlers -- which is the element where the click first happened. 
It appears in all three handlers because all of them are essentially handling the exact same event (because of event 
bubbling). 


e.currentTarget - not the same. the currentTarget is exactly the same as the this keyword. 


// stop propagation

e.stopPropagation(); -- Only the background color of the clicked link has changed. The parent elements will not change their background color, which means that the event never arrived at those elements. In practice, it is usually not a good idea to stop propagation. 
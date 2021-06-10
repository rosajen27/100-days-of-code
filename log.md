# 100 Days Of Code - Log

### Day 1: April 15, 2021

**Today's Progress**: Spending some time this week revewing and studying how JavaScript works behind the scenes in order to solidify previously learned concepts. 

Today's study session included: 
    1. JavaScript Engine and Runtime
    2. Execution Context and the Call Stack
    3. Scope and The Scope Chain.


### Day 2: April 16, 2021

**Today's Progress**: Spending some time this week revewing and studying how JavaScript works behind the scenes in order to solidify previously learned concepts. 

Today's study session included: 
    1. Variable Environment: Hoisting and The TDZ


### Day 3: April 17, 2021

**Today's Progress**: Spending some time this week revewing and studying how JavaScript works behind the scenes in order to solidify previously learned concepts. 

Today's study session included: 
    1. The this Keyword


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


### Day 5: April 19, 2021

**Today's Progress**: Practiced destructuring objects in isolation

**Thoughts**:To destructure objects we use the curly braces. Then all we have to do is to provide the variable names that exactly match the property names that we want to retrieve from the object. The order of elements does not matter - so we do not have to manually skip elements like in an array. Helpful when retrieving elements from an object when using APIs


### Day 6: April 20, 2021

**Today's Progress**: Practiced implementing The Spread Operator (...) in isolation

**Thoughts**: We can use the spread operator to basically expand an array into all its elements (unpacking all the array elements at once)


const arr = [7, 8, 9];


const badNewArr = [1, 2, arr[0], arr[1], arr[2]];


console.log(badNewArr); → [1, 2, 7, 8, 9]



const newArr = [1, 2, ...arr];
console.log(newArr); → [1, 2, 7, 8, 9]



Same exact results. What the spread operator does is to basically take all the values out of this arr array and then write them individually as if we wrote 7, 8, 9 manually.


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


### Day 9: April 23, 2021

**Today's Progress**: Short Circuiting (&& and ||)

**Thoughts**: In the case of the OR operator, short circuiting means that if the first value is a truthy value, it will immediately return that first value. 


In the case of the AND operator, it works in the exact opposite way of the OR operator. The AND operator short circuits when the first value is falsy, and then immediately returns that falsy value without even evaluating the second operand.


### Day 10: April 24, 2021

**Today's Progress**: The Nullish Coalescing Operator (??)

**Thoughts**: The Nullish Coalescing Operator works with the idea or with the concept of nullish values instead of falsy values. Nullish values are null and undefined. It does not include zero or the empty string.


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


### Day 23: May 7, 2021

**Today's Progress**: Functions: How Passing Arguments Works - Value vs.
Reference

**Thoughts**: When we pass a primitive type as an argument on a function, the function makes a copy of the ORIGINAL VALUE, and works with it.


On the other hand, when we pass an object as an argument on a function, the function makes a copy of the REFERENCE that points to the place of the memory where the object is stored. This copy is a value itself, not a reference. Because of all of this, the original object can be modified from inside of a function.


- In programming languages, Arguments can be passed by value, or passed by reference

- JS does not have passing by reference, only passing by value

- So, when we pass primitive values, the function works with a value, which is a copy of the original value

- When we pass an object, the function works with a value that address to the spot where the original object is in the memory (still is not a reference)


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

### Day 27: May 11, 2021

**Today's Progress**: Immediately Invoked Function Expressions (IIFE)

**Thoughts**: Sometimes in JavaScript, we need a function that is only executed once, and then never again. So basically a function that disappears right after it’s called once. We can trick JavaScript into thinking that this anonymous function is an expression by wrapping it in parentheses and then calling it.


(function() {

	console.log(“This will never run again.”);

})();


(() => console.log(“This will ALSO never run again”))();


Why was this pattern invented? We already know that functions create scopes. It is important to note that one scope does not have access to variables from an inner scope. Therefore, we say that all data defined inside a scope is private and encapsulated. Data encapsulation and data privacy are important concepts in programming.


Many times we need to protect our variables, from being accidentally overwritten by some other parts of the program, or even with external scripts or libraries.


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



### Day 32: May 16, 2021

**Today's Progress**: Begin developing Bankist App

**Thoughts**: Through the development of this application, I will have the opportunity to apply concepts I have learned about functions and arrays. Bankist is a fictitious and minimalist online banking application that allows the user to:


- Log in with a username and password
- View and sort their monetary movements
- Transfer money to another account
- Request a loan from the bank
- Delete their account


GitHub Repo: https://github.com/rosajen27/bankist


### Day 33: May 24, 2021

**Today's Progress**: (Personal Note: I took several days off from coding last week due to an unexpected loss in the family. 💔)


Spent some time today reviewing previous learning about arrays in order to complete a coding challenge. 

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


### Day 35: May 26, 2021

**Today's Progress**: Polishing Portfolio, GitHub, and Resume

**Thoughts**: With 3 weeks left of the 2020-2021 school year, I will be utilizing this upcoming summer break as an opportunity to begin the application process. I aspire to transition from a k-6 educator to a front end web developer.

✨ Portfolio: https://rosajen27.github.io
👾 GitHub: https://github.com/rosajen27
📄 Resume: https://bit.ly/2Svsirg


### Day 36: May 27, 2021

**Today's Progress**: The Map Method

**Thoughts**: The Map method is another way we can loop over arrays. Unlike forEach, the Map method will give us a brand new array. This new array will contain in each position the results of applying a callback function to the original array elements.


With the Map method - besides the current array element, we also get access to the current index as well as the whole array.


Applied this new knowledge into Bankist App Project

GitHub Repo: https://github.com/rosajen27/bankist

- Used the Map method to convert EUR to USD
- Used the Map method to return movement descriptions


### Day 37: May 28, 2021

**Today's Progress**: Using the Map and forEach method to computer usernames for each account owner in Bankist App.

GitHub Repo: https://github.com/rosajen27/bankist

**Thoughts**: The username will be the initials of each of the four users.


const user = "Steven Thomas Williams"; // stw

const username = user.toLowerCase().split(" ").map
(function(name) {

  return name[0];

}).join("");


### Day 38: May 29, 2021

**Today's Progress**: Using the Filter Method to filter out negative values (withdrawals) in Bankist App.

GitHub Repo: https://github.com/rosajen27/bankist

**Thoughts**: The Filter Method is used to filter for elements that satisfy a certain condition by using a callback function.


// filter out negative values (withdrawals)

const deposits = movements.filter(function(movement) {

	return movement > 0;
	
});


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


### Day 41: June 8, 2021

**Today's Progress**: Continued to practiced Chaining Methods together in Bankist App.

GitHub Repo: https://github.com/rosajen27/bankist

**Thoughts**: Chained filter, map, and reduce methods to create calcDisplaySummary function in order to display a summary of all deposits, withdrawals and interest earned in the user's account. Interest only applies if balance is equal to 1 or greater.


Important Notes: 


We should not overuse chaining, and instead optimize it. Chaining many methods one after the other can cause performance issues if using large arrays. 

It is a bad practice in JavaScript to chain methods that mutate the underlying original array. An example of that is the splice or reverse methods. 


### Day 42: June 9, 2021

**Today's Progress**: Chaining Methods Coding challenge provided by Jonas Schmedtmann's JavaScript Course.

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
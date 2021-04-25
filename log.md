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

**Today's Progress**: 

**Thoughts**:
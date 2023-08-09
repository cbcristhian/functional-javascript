# Pure Functions

A pure function has two characteristics:

* ### No side effects: 
    A pure function has no effect on the program or the world besides outputting its return value
* ### Deterministic:
    Given the same input values, a pure function will always return the same output. This is because its return value depends only on its input parameters, and not on any other information (e.g. global program state)

```Javascript
const thesis = {name:"Church's", date: 1932}

function renameThesis(oldThesis, newName){
    return {
        name:newName, date: oldThesis.date
    }
}
```
In this example the function only depends on the arguments that are passed in, not in the global variable and external data.

Another example to compare would be:

## Not Pure

```Javascript
let name = "Arthur"

function greet(){
    console.log(`Hello, ${name}`)
}

greet(); //Hello, Arthur

name="John";
greet(); //Hello, John
```

## Pure

```Javascript
function greet(name){
    return `Hello, ${name}`
}

greet("Arthur"); //Hello, Arthur

greet("John"); //Hello, John
```

# Higher Order Function

In functional programming, a Higher Order Function (HOF) is a function that either takes one or more functions as arguments or returns a function as its result. In other words, Higher Order Functions treat functions as first-class citizens, allowing them to be manipulated and used just like any other data type.

Is a function takes in another or a couple of functions as inputs
First Class Functions are can be passed as arguments.

Higher Order Functions like `map, reduce, filter` are used instead of using loops.


```Javascript
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

//filtering even numbers
const evenNumbers = numbers.filter((num) => num % 2 === 0);

console.log(evenNumbers); // Output: [2, 4, 6, 8, 10]


```

# Inmutability

Immutability in JavaScript refers to the concept that once a value (such as an object, array, or string) is created, it cannot be changed. Instead of changing the existing value, new values ​​are created based on the original value. This is important to ensure predictability and stability in the schedule, as it prevents unwanted side effects and makes it easier to track changes.

## Do Not Mutate, Copy

```Javascript
const originalArray = [1, 2, 3];

originalArray.push(4);

console.log(originalArray); // Output: [1, 2, 3, 4]

```
In this example you are changing the original data, mutating its value.


Let's see an example of inmutability
```Javascript
const originalArray = [1, 2, 3];

const newArray = [...originalArray, 4];

console.log(originalArray); // Output: [1, 2, 3]
console.log(newArray);      // Output: [1, 2, 3, 4]

```

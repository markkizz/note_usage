# Javascript

## Variables
- var
    - global scope
- let
    - block scope
- const
    - block scope and cannot overwrite it

## Array of Objects & JSON
```
//array of object [{}, {}, {}];
const todo = [
    {
        id: 1,
        text: 'brah',
        isComplete: true
    }
    {
        id: 3,
        text: 'brah brah',
        isComplete: true
    }
    {
        id: 3,
        text: 'brah brah brah',
        isComplete: false
    }
];
***
//access -> arr[in].propOfObj , arr[in]["propOfObj"]
console.log(todo[0].id);//1
- arr.obj -
***

//JSON method
const todoJSON = JSON.stringify(todo);
console.log(todoJSON);// return JSON file

//loop through array of obj
for(let valueInArray of todo){
    console.log(valueInArray.id);//same as $ todo[i].id
}
```

## Fancy Loop

### for ..in & for ..of

    // array
    //if use for ..in loop through array you wiil get index of array
    const arr = [item1, item2, item3]
    for(let i in arr) {
        console.log(i); //log: 0 1 2
    }
    for in array index -> for in in

    //if you use for ..of loop through array you will get value
    let arrAnimals = ['🐔', '🐷', '🐑', '🐇'];
    for(let animal of arrAnimals) {
        console.log(animal);    //log: 🐔, 🐷, 🐑, 🐇;
    }
    for of value in array -> for of val

    for of suit with array
    for in suit with obj


### higher order function

    forEach(), map(), filter()
    it use with function expression
#### forEach()

    //forEach() -> get array value through fn expression
    const arr = [item1, item2, item3];
    arr.forEach(function(val) {
        console.log(val)    //log: item1, item2, item3
    });

    //if use in array of object
    todo.forEach(function(todoIndex) {
        console.log(todoIndex.id)   //return value of obj in array
    })

    //use arrow fn
    todo.forEach(todoIndex => console.log(todoIndex.id))    auto return with single code line

#### map()

    //map will return an array that we should assign in var
    const todo = [
        {
            id: 1,
            text: 'brah',
            isComplete: true
        }
        {
            id: 3,
            text: 'brah brah',
            isComplete: true
        }
        {
            id: 3,
            text: 'brah brah brah',
            isComplete: false
        }
    ];

    const todoText = todo.map(function(todo) {
        return todo.text    //this will return only text and group it to array
        //log: ['brah', 'brah brah', 'brah brah brah'];
    })

### filter()

    //filter will return an array element that we want it
    const todoComplete = todo.filter(function(todo) {
        return todo.isComplete === true;    //this will return todo array that have isComplete true
        //log: [{... isComplete: true}, {... isComplete: true}]
    })

#### Combine
    const todoComplete = todo.filter(function(todo) {
        return todo.isComplete === true;
    }).map(function(todo) {
        return todo.text;
    })

    //short hand
    const todoTextAndFilter = todo.filter(todo => todo.isComplete === true;).map(todo => todo.text;)
    //filted array whth complete true than group them with array only text

## Math Random
```
// This random number function that will creates color codes for the randomColor variable
function rgb(num) {
    return Math.floor(Math.random() * num);
}

// Write your code below
let colorChange = function (event) {
    let randomColor = 'rgb(' + rgb(255) + ',' + rgb(255) + ',' + rgb(255) + ')';
    event.target.style.backgroundColor = randomColor;
}

button.onclick = colorChange;
mysteryButton.onwheel = colorChange;
```
------------------------------------//-----------------------------------





















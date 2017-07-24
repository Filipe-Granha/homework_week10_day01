# JS Day 1 Homework

Go through each sample code and work out what the output will be and explain what happened.

### Episode 1
```js
var name = 'Keith';

var printName = function() {
  console.log('My name is ' + name );
};

printName();






Answer...
Keith is a global variable, since it's declared outside of any function.
Thus, it is accessible to the function printName, and the output will be:
My name is Keith




```

### Episode 2
```js
score = 5;

var result = function() {
  var score = 3;
  return score;
};

console.log(result());






Answer...
There is a global variable (I think, even though it doesn't use the keyword 'var'?), 5.
Then, inside the function result, there is another variable with the same name(score), with the value of 3, which in this case will override or shadow the global var.
Therefore, the output will be 3.




```

### Episode 3
```js

var myAnimals = ['Chickens', 'Cats', 'Rabbits'];

var listAnimals = function() {
  myAnimals = ['Ducks', 'Dogs', 'Lions'];
  for(var i=0;i<myAnimals.length; i++){
    console.log(i + ": " + myAnimals[i]);
  }
}

listAnimals();





Answer...
There is a global variable, myAnimals (an Array of strings).
Inside the listAnimals function, there is another variable with the same name, not using the keyword 'var'.
Because of that, this second variable will not only override the first one, but instead it will replace it.
The output will be:
0: Ducks
1: Dogs
2: Lions




```

### Episode 4

```js

var suspectOne = 'Jay';
var suspectTwo = 'Val';
var suspectThree = 'Keith';
var suspectFour = 'Rick';

var allSuspects = function() {
  var suspectThree = 'Harvey'
  console.log('Suspects include: ' + suspectOne + ', ' + suspectTwo + ', ' + suspectThree + ', ' + suspectFour)
};

allSuspects();
console.log( 'Suspect three is:' + suspectThree );





Answer...
4 global variables.
1 variable inside the function, same name as one of the global variables (suspectThree), which will therefore shadow it, but only inside that function.
Output will be:
Suspects include: Jay, Val, Harvey, Rick
Suspect three is: Keith.






```

### Episode 5

```js

var detective = {
  name : 'Ace Ventura',
  pet : 'monkey'
};

var printName = function(detective) {
  return detective.name
};

var detectiveInfo = function() {
  detective['name'] = 'Poirot'
  return printName(detective);
};

console.log(detectiveInfo());





Answer...
var detective is a global variable (defined outside the scope of any function), representing a Hash.
The second function(detectiveInfo), is attributing a new value to the key 'name', Poirot.
Without runnig this, I would say that since detective is a global variable, and can be overshadowed, it can maybe also be changed, as we are seing trying to be done in function detectiveInfo.
If this is true, when returning function printName, the output will be Poirot.
..
Apparently this confirms, as after running the code the output is indeed Poirot.








```

### Episode 6
```js

var murderer = 'rick';

var outerFunction = function() {
  var murderer = 'marc';

  var innerFunction = function() {
    murderer = 'valerie';
  }

  innerFunction();
}

outerFunction();
console.log('the murderer is ', murderer);





Answer...
Global variable murderer.
Function outerFunction, with variable murderer, which shadows the global one.
Another function, innerFunction, inside the outerFunction, without keyword 'var', which I would say will not replace the global variable, as its scope is only inside the outerFunction, and it will then only shadow the variable murderer from the outerFunction.
Therefore, the output should be:
valerie
the murderer is rick
..
After running the code, it's confirmed 'rick' is the answer, even though I was wrongly led to believe that we would also see valerie in the output, but obviously there is no console.log command for that to happen.






```

### Episode 7 - Make up your own episode/s!

Make up your own episode which can be whatever you wish and the rest of the class will work out together what happened and what the output will be.




Answer...

var electricCar = "Tesla";

var carFunction = function() {
   electricCar = "Toyota"
  console.log("Guess which electric car will this output? " + electricCar + "!")

  var anotherElectricCarFunction = function() {
     var electricCar = "Honda"
    console.log("Do you prefer " + electricCar + "?")
  
  var yetAnotherElectricCarFunction = function() {
    var electricCar = "BMW"
  }
  };
}
carFunction();
console.log("Which one will it be this time? " + electricCar + "!");



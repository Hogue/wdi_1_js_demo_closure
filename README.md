![General Assembly Logo](http://i.imgur.com/ke8USTq.png)


## Closure

Closure is the property of function such that it can access variables is the same scope it was declared in. Even when that function is operating outside of that scope.

**Create a file `js/sayHelloGenerator.js`**

```
function sayHelloGenerator(){
  var prefix = "Hello ";

  function hey(name){
    return prefix + name;
  };

  return hey;
};

var sayHey = sayHelloGenerator();

// "Hello Bart" 
var msg = sayHey("Bart");
console.log(msg);
```

## Lab.

1. Write the Scope diagram built during Compilation.
2. Write the Runtime/Execution steps for the above. 

## Demo
Another example.

**Create a file `js/makeAdder.js`**

```
function makeAdder(x) {
  return function(y) {
    return x + y;
  };
}

var add5 = makeAdder(5);
var add10 = makeAdder(10);

console.log(add5(2));  // 7
console.log(add10(2)); // 12
```

The key to understanding closure is to know that a function declared in a scope can **ALWAYS** access other variables in that scope.

**Even when that function is executing outside of the declaring function**

## Lab

In this file, `js/makeMultipliers.js` create two multiply functions *(same as above, just using multiplication)* :  

1. Create a function named "multiplierFactory". This function will take one parameter. This will the first number in the multiplication. For example:

	For (x * y), 'x' will be the only 'multiplierFactory parameter.  
	
2. Create an inner function that will take one parameter. This will be the second number, 'y', in the multiplication.

3. Return the inner function.

4. Create a function that will multiply 6 to it's argument.
5. Create a function that will multiply 13 to it's argument.
6. Use these multiply functions and log out results.

## Demo

**Create a file `js/show_name_closure.js`**

```
function showName (firstName, lastName) {
  var nameIntro = "Your name is ";

  function makeFullName(){     return nameIntro + firstName + " " + lastName;   };

  return makeFullName; };

// Your name is Michael Jackson
console.log(showName ("Michael", "Jackson")());
```

We are invoking the function returned immediately:  
                                        
1. showName(("Michael", "Jackson") returns a function. It's makeFullName function.  

2. makeFullName function is invoked by the last pair of parens.  
	`showName(("Michael", "Jackson")()`  
	          
3. The string produced/returned is printed to the console.  **Notice the last empty set of parens ()** this invokes the function being returned from showName.
  `console.log(showName ("Michael", "Jackson")());`
  
  
## Lab

Re-write the last lab to use an immediately invoke functions.
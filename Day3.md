![Web Rendering Block Diagram](https://www.html5rocks.com/en/tutorials/internals/howbrowserswork/webkitflow.png)
 
**Q1. Rendering of Websites**  
Rendering of a website refers to displaying the contents visible on the browser screen. It communicates and requests information from the network of the browser and parses the HTML or CSS code from the server to the engine.  

Parser - As seen from the block diagram, the HTML and CSS code are taken from the server and parsed using the HTML and CSS parser. 
Attachment - This attaches the HTML and CSS code to the rendering engine.
Layout - this takes input from the browser and passes them to the rendering engine.
Render Tree - this takes HTML code and interprets it into what you see visually.
Painting - Each node of the render tree is drawn out on the screen by communicating with the Operating System Interface which contains designs and styles for how UI elements should look.
User Interface - This displays the final output on the browser screen.

  **Names of JS Engines and their creators -**
  1. V8 Engine created by Chrome (Google)
  2. JS Core created by Safari (Apple)
  3. Chakra Core created by Microsoft
  

  **Q2. Difference between Interpreter and Compiler**  
  
  Interpreter -   
1. It interprets the language every time.
2. An interpreter executes the code line by line individually, and not as a whole like the compiler.
3. It interprets the instructions directly in the programming language.
4. JavaScript is an interpreted language.

  Compiler - 
1. It compiles the code only once.
2. A compiler converts the source code (high-level programming language) into a byte code (low-level programming language) and is then executed by the computer.
3. After converting the program code into byte code, the program does not need to go through compilation again.
4. Java is a compiled language.

  **Q3. Different ways of defining a variable**
  
  There are three ways to declare variables in JavaScript, they are - **let**, **const** and **var**, where let, const and var are keywords.
  
  Declaring a variable using **let**- By using the let keyword to declare a variable, the value of the variable can be changed anytime in the code.
  
 Assigning a value to the variable:
 let variable_name = value;  
 *Example :*  
 let a = 1;  
 console.log(a); //passing the value of a to the console, this results in displaying the value of variable a
 
 
 Declaring a variable using **const** - By using the const keyword, the value which is once defined in the code cannot be changed.
 
 Assigning a value to the variable:  
 const variable_name = value;
 *Example :*
 const pi = 3.14; //the value of pi cannot be changed anywhere in the code
 console.log(pi);

 Declaring a variable using **var** -   
 var variable_name = value;
 *Example :*
 var b = 3;
 
 Disadvantages of **var** keyword:  
 Using the var keyword to declare a variable in JavaScript is not recommended as it might accidently overwrite an existing global variable.
 
 **Q4. Types of Scopes in JavaScript-**
 
 The scope of a variable determines its accessibility. It refers to how the variables can be accessed in a program. There are 3 types of scopes in JavaScript-  
 They are -  
 
 1. Global scope - A variable declared globally is called a global variable. This variable, therefore, has a global scope that is, it can be accessed by all the other functions in a program.
 
 *Example:*  
 let a = "hello";
 console.log(a)
 
 function try() {
    console.log(a);
 }
 
 //from the above example, it can be seen that the variable a can be accessed from anywhere in the code
 
 2. Block scope - A variable declared locally is called a local variable. These variables exist only in that block. The blocks outside of this particular block can not access the variable declared there.
 
 *Example:*  
 if(true) {
    let a = 1;
    var b = 2;
 }//this is a block
 
 
 3. Functional scope - A variable declared in a function can be accessed within that function only. 
 
 *Example:*
 function try() {
    let a = "hello";
    console.log(a);
    //the variable a can only be accessed by this function
 }
 
 function new() {
    //this function can not access the variable a
 }
 
 //the code outside of the function also can not access the variable in try() unless the function try() is called separately like  
 //try();  
 //console.log(a);
 
 **Q5. Types of Functions**

Defining a normal function: The "function" keyword is required to declare the normal function  
function function_name() {
  //function body
}

function-name(); //calling the function

In a normal function, the 'this' keyword is used to access a particular key. The 'this' kewyord refers to variables in a global scope. We define 'this' in a normal function like:  
*Example:*  
function getFullName() {
    return this.firstName + " " + this.lastName;
}

Defining a no-name or an anonymous function: As the name says, this function does not require a function name.
let a = function() {

}

Defining an arrow function:
function_name = () => {

}

In an arrow function, the 'this' keyword refers to a global object and hence should not be used in functional scope for defined values. When we define 'this' in a class, its parent is class and when we define 'this' in an object its parent is global. We declare 'this' keyword in a manner similar to all the other functions.

getFullName = () => {
    return `${this.fname} ${this.lname}`; \\this is string concatenation using this
}


**Q6. NodeJS**

NodeJS is an open-source, server side platform runtime environment for developing networking applications using JavaScript.  
Features of NodeJS:  
1. Asynchronous and Event Driven
2. Very Fast
3. Single Threaded but Highly Scalable
4. No Buffering

Event loop:  
The event loop is what allows Node.js to perform non-blocking I/O operations — despite the fact that JavaScript is single-threaded — by offloading operations to the system kernel whenever possible.  
When NodeJS starts, it initializes the event loop. The event loop's order of operations includes six phases.  
1. timers: this phase executes callbacks scheduled by setTimeout() and setInterval().
pending callbacks: executes I/O callbacks deferred to the next loop iteration.
2. idle, prepare: only used internally.
3. poll: retrieve new I/O events; execute I/O related callbacks (almost all with the exception of close callbacks, the ones scheduled by timers, and setImmediate()); node will block here when appropriate.
4. check: setImmediate() callbacks are invoked here.
5. close callbacks: some close callbacks, e.g. socket.on('close', ...).

Between each run of the event loop, Node.js checks if it is waiting for any asynchronous I/O or timers and shuts down cleanly if there are not any.

**Q7. Promise**
Promises are used to handle asynchronous operations in JavaScript. They are easy to manage when dealing with multiple asynchronous operations where callbacks can create callback hell leading to unmanageable code.

Creating a promise:  
let a = new Promise ((resolve,reject) => {
    resolve(data); //if data is success
    reject(data); //if error occurs
})

For resolve, we need a 'then' clause:  
a.then((value) => {
  console.log(value);
})

For reject, we need a 'catch' clause as error is detected in the program but we need to declare both the clauses as which clause will be called when is not known.  
a.then((value) => {
  console.log(value);
}).catch((value) => {
  console.log(value);
})


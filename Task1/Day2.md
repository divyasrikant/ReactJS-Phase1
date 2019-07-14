 ![Web Rendering Block Diagram](https://www.html5rocks.com/en/tutorials/internals/howbrowserswork/webkitflow.png)
 
**Rendering of Websites**  
Rendering of a website refers to displaying the contents visible on the browser screen. It communicates and requests information from the network of the browser and parses the HTML or CSS code from the server to the engine.  
As seen from the block diagram, the HTML and CSS code are taken from the server and parsed using the HTML and CSS parser.

  **Names of JS Engines and their creators -**
  1. V8 Engine created by Chrome (Google)
  2. JS Core created by Safari ( Apple)
  3. Chakra Core created by Microsoft
  

  **Difference between Interpreter and Compiler**  
  
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

  **Different ways of defining a variable**
  
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
 
 **Types of Scopes in JavaScript-**
 
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
 
 **Types of Functions**

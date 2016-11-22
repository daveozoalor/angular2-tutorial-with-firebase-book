# Angular2 ebook

This book is currently being developed. Its not ready yet, but in this book, I'll be teaching how o 
create an applicaion using Angular2 using several backend technologies starting with firebase.  Your PR is highly welcome.




ANGULAR2 + Firebase 3 Tutorial
=================

###Who

I'm Dave Partner Ozoalor.  I'm a software engineer & developer evangelist at [Davepartner.com](http://davepartner.com), and I've been teaching lots of programming languages on [Youtube](http://youtube.com/c/braintemorg). 
And I want to teach you now.
Because you're good looking.
And because it's useful.

##What is AngularJs
Angularjs is an opensource javascript framework for build mobile and web applications using HTML and Javascript. Angularjs is managed by Google. Its widly rated as the most popular javascript framework for building mobile and web applications.

##What is Angular2
Angular2 is the second and latest version angularjs recently released by Google. Its much easier to learn and comes with many powerful features such as effective data management, HTTP services, form handling, fast template rendering and every other tool you need to build complex frontend web applications. You can also fuse any backend technologies you are good with into angular2 without any hassles such as firebase,couchdb, pouchdb, mongodb, nodejs and so on.  
Angular2 was built with mobile devices first in mind which means it takes a mobile first approach.

##Audience
This book is written for novices and proffessionals who wish to learn how to build fast and scalable frontend applications for mobile and the web. This book will take your knowledge of Angular2 from basics to proffessional. Suitable examples will be used to describe aspects of angular2.

##Prerequisites
A BASIC understanding of the following will suffice:
* 1. HTML
* 2. CSS
* 3. Javascript .Angular2 uses a special kind of javascript called Typescript, that's what we will be treating first in this book so you do not need to know a lot of javascript to learn angular2. 
* Knowledge of Angular 1 is NOT required. You can just jump right in and start learning how to build apps with angular2.


##Table of conents
* Editors
* Installation and Setup
	* Installation and Setup 
		* Nodejs Installation
		* Angular CLI Installation
		* Atom Text Editor Installation
	* Installation
	* Install Typings
	* Create New Angular 2 Project
* ES6/Typescript
	* Variable declaration
	* Classes
	* Template Strings
	* Arrow Functions
	* Promises
* Components
* Inputs
* Outputs
* Lifecycle
* Templates
* Events
* Forms
* ViewChild

###Text Editors and IDEs

The first thing you'll need is an environment to write your code. There are many Integrated Developmemt Environments (IDE) you can use. However, the below are the ones I use.  

 * Your current IDE. If you have ever written any HTML code then you can keep using that IDE you used to write the code.
 * [Notepad++](https://notepad-plus-plus.org/download/v7.2.html) - This is lightweight, simple and will get the job done. 
 * [Sublime Text ](https://www.sublimetext.com/download) - Really superb, lightweight and smart too.
 * [Aptana Studio 3](http://aptana.com/) 
 * [Atom.io](https://atom.io/) - This is my new found love, it has really powerful features to make your code easy. I combine it with codelobster, link below.
 * [CodeLobster](http://www.codelobster.com/download.html) - I really like this code editor when ever I am write html, css and javascript codes because of its amazing syntax highlighting and code folding that comes as default settings.
You just need one of the above listed IDEs. 

There are many others [listed here](http://en.wikipedia.org/wiki/List_of_HTML_editors), you can check them out.

### Installation and setup
In this chapter we will be going through the installation and setup of our first angular 2 project. We will be making use of a fine combination of Nodejs and Angular-CLI as an easier and more effective way to build angular 2 applications. 

#### Nodejs 
The first thing we will be installing is called Nodejs. Nodejs is a platform for building fast and scalable applications. Its built on top of Chrome's powerful runtime. 
To install Nodejs, visit [Nodejs.org](http://nodejs.org) and download the latest stable version and install it on your system. If you want to learn more about Nodejs at a later time, feel free to take my [Nodejs tutorial](https://www.youtube.com/watch?v=JoCoXXqBCvQ&list=PLnBvgoOXZNCPEEN6BtSu6O3yf0CDA7pjb) on youtube.

#### Angular-CLI
Angular-CLI stands for Angular command line interface, its a command line interface for building angular applications using nodejs style modules. Its easier, less noisy and more automatic than just building Angular apps from scratch. Angular-CLI takes the pain of manually creating files and typing out certain default codes off yoru shoulders. 
 
Once your Nodejs installation is complete, open your command prompt and type `npm install -g angular-cli`. 
If you don't know how to open your command prompt, just click on your windows start menu and type `cmd`, or type `node` then click on the windows command prompt that will show up. 
When the window shows up, just type `npm install -g angular-cli`. If you have any errors, its probably because you have not installed nodejs or you have not restarted your system after the installation.

#### Create New Angular 2 Project
We will be using Angular-CLI to create our first angular2 project. To do that, navigate to the folder you'd like to create your angular project in and run this command on your command prompt  `ng new angular2-blog`.  After which you navigate into the project folder by running `cd angular2-blog`.
Note that `angular2-blog` is the name we want to give our new app. You can name yours anything. But the syntax remains `ng new <name of project`.
In case you don't know how to navigate to the correct project folde using your command line, here is how to do it:
open your command prompt and type `cd <path to project directory`. For me, since I want to create my project on my desktop, I'll simply type `cd C:\Users\dell\Desktop\`. Then hit enter. 

#### Typings 
Typings is a definition manager for Typescript, it helps you install Typescript definitions. Typings makes use of a file named typings.json that resolve to the Typings NPM, Bower, Registry, GitHub, HTTP and local files. Packages can use type definitions from various sources and different versions without conflict.
So install Typings by typing `npm install -g typings`. 

#### Firebase 
Firebase is a backend as a service that can be plugged into any application and any platform. Firebase contains a bundle of packages most apps need some of which are notification system, NoSql database, crash reports, admob, user authentication system and so on. Angular 2 just builds the frontend of your app for you, we will still need a backend to handle the above. We will be using firebase in this tutorial. Other alternatives of firebase are MongoDB database, One signal notification, couchDB and so on. As you can see it is hard to find it all in one bundle like firebase did. 
The only real downside of Firebase is that your app cant function offline like some mobile apps may need such as game and notepad.
We'll be needing Firebase further down the tutorial but let's just install it now.

So open your command prompt, navigate to your project folder if you are not already there and type `npm install --save firebase`. 
This installs firebase into your project. We also need to typings for Firebase.

To install Typings definition for Firebase run `typings install --save firebase` on your command prompt, be sure you are still in the project folder. 
You can read more about Firebase  [here on npm](https://www.npmjs.com/package/firebase) and their official [Firebase documentation](https://firebase.google.com/docs/).  

#### Viewing your app
To view the app we need to spin up a server. To do that, be sure you are on your projects folder, run `ng serve`. Your server will come up and and display the url you can use to view the app on your browser. Mine is `http://localhost:4200/`. Copy it and paste in your browser then hit enter.


##Introduction to ES6/Typescript
Typescript is a new powerful programming language built and maintained by Microsoft, it is a superset of javascript and comes with very powerful features such as static typing and class-based object-oriented programming. Google chose to build Angular2 on Typescript instead of its other alternatives such as babel, atScript and Dart. If you visit Angular2's official documentation section you can Angular2 documentation for javascript and [Dart](https://angular.io/docs/dart/latest/index.html) incase for some reason you wish to go with those.

ES6 is the next version of JavaScript that was just recently approved. It comes with a ton of new ways to write JS. However, its downside is that it has not been fully implemented by many browsers. ES7 is also in the pipeline. 
Most browsers only understand javascript upto ES5, which is the normal javascript most people code. When building angular2 applications with typescript (ES6), your browser still needs to have the code compiled to ES5 javascript before it can understand it. There are two main transpilers that do this job:
* [Traceur](https://github.com/google/traceur-compiler) - Owned by Google
* [Babeljs](https://babeljs.io/) - Babel is more popular 

We are taking time to explain most of these terminologies here in the beginning so that when we start writing actual code, it will be less boring because we won't have much explanations to make. We'll go through a quick typescript tutorial just to familiarize you with the code we'll be writing for the rest of this tutorial.

### Variable Declaration in Typescript
VAR in ES5 javascript, variables are declared with the `var` keyword. The problem is that this keyword does not properly scope the variables. A good example is when you declare a variable in a loop you are using. The variable may sometimes still be available after the loop thereby pottentially messing up your whole code. Below is an example:
``` 
for (var j = 0; j <= 1; j++){
	//j is available here
}
//unfortunately, j is also available here
```

LET in Typescript,  in Typescript, variables are declared with the `let` keyword, forcing them to stay available only within the scope they are defined in. This prevents that unnecessary overflow, and is perfect for functions and closures. Let's look at the above function once again using let.
```  
for (let j = 0; j <= 1; j++){
	//j is available here
}
// J is not available here

```
Nice! So its adviced you use `let` whenever necessary. 

### Function Types in Typescript
In Typescript, function paramters need to be typed and are all required by default. Below is an example of a function that takes in 3 parameters `firstname` , `middlename` and `lastname`.

```
function fullname(firstname : string, middlename = "partner", lastname? : string){
      
      //firstname = required
      //middlename = will resolve to 'partner' if not provided when the function is being called
      //lastname = optional because of the '?' sign right after the parameter
      //they all bear the type 'string'.

}
```
* Note that, required parameters must come before the optional parameters. if we wanted firstname to be optional,we would have to exchange its position withe `middlename` since middle name has a default value. 

From the above, here are valid ways to call the above function:
```
fullname("Dave") //correct
fullname("Dave", "Young") // correct
fullname("Dave", "Young" , "Money") //correct
fullname(undefined,"Young") //correct
fullname() //error, too few parameters
fullname("Dave","Young", "Money", "Xing") //error, too many parameters
```
There are a couple of other tweaks to note in Typescript functions, but we will not cover them all here since this is not primarily a typescript function.

####Arrow functions 
Fat arrow functions in Typescript helps write shorter cleaner functions. Here is a comparison between a function written in javascript and the same function replicated in Typescript.

```
//Javascript
class Car {
  constructor() {
    this.carName = 'Volvo';
    
    	var that = this;
	setTimeout(function() {
	  console.log(that.name); //we used "that" to make reference to the outer "this" context
	});
  }
}
```
Let's see this same function in Typescript:

```
//Typescript
class Car {
  constructor() {
    this.carName = 'Volvo';
    
    setTimeout(() => {
      // This fat arrow function binds to the current "this" context context. So this will print "Volvo"
      console.log(this.carName);
    });
  }
}
```

### Classes in Typescript

Typescript leverages ES6 features to give developers the ability to use object-oriented class-based approach to building reusable components rather than the traditional functions and prototype-based inheritance as the basic means of building up reusable components. 
Let's see a quick example here:

```
class Drive{
	car: string;
	
	constructor(carName : string){
		this.car = carName;
		
		this.aboutCar();
	}
	
	aboutCar(){
	console.log("Your car name is " + this.car);
		return this.car; 
	}

}

let drive = new Drive("Toyota");
```

As you can see above, we have a class named `Drive` with 3 members. We refer to each of the members using the `this` keyword. `this` denotes that its a member access.

In the example above, you may notice that we have accessed each member freely without using either the public, private or modifier. That is because in Typescript it is not required unlike in some languages such as C#. By default, all members in Typescript are public. Although you can still explicitly declare them as `public`. `private` or `protected`.

Example of the above code with members explicitly declared as public:
```
class Drive{
	public car: string;
	
	public constructor(carName : string){
		this.car = carName;
		
		this.aboutCar();
	}
	
	public aboutCar(){
	console.log("Your car name is " + this.car);
		return this.car; 
	}

}

let drive = new Drive("Toyota");
```
If you mark a member as `private`, it cannot be accessed from outside of its containing class


### Template Strings
Typescript gives you the ability to write long or multi-line inline strings which is not possible in the good old ES5 javascript without concatenation. Here is what I mean:

```
//In Javascript 
var variable1 =  'I love Dave Partner\'s '+
                 'blackberry phones that are'+
		 'all good in color';
```
As you can see, we had to use concatenation to join each of the line in order to avoid errors. In Typescript, you'd just need to use back ticks, one at the beginning and one at the end. The back tick key is directly above the tab key on your keyboard. Here is the same code in Typescript:

```
//In Typescript 
var variable1 =  `I love Dave Partner\'s 
                 blackberry phones that are
		 all good in color`;
```

Here is another more detailed Typescript example with data binding:

```
let eatery_name = 'Dave Delicious';
let city_name = 'Dave Delicious';

let template = `
  <div>
    <h2>${eatery_name} Eatery</h2>
    <p>
      The best Eatery in the whole ${city_name} city.
    </p>
  </div>
`;
 ```

###Promises In Typescript
Typescript uses the concept of promises to provide a unique way to write asynchronous functions. Here is a good example of an attempt to fetch data froom an api, print the results or print the error.

```
loadListOfCars() {
  fetch('goto/ourapi/cars').then((response) => {
    return response.json(); //convert our resonse to json
  }).then((data) => {
    this.cars = data; //save it in a variable called this.cars
  }).catch((error) => {
    console.error('Error fetching users', error); //print any errors
  });
}
```
We'll be seeing lots of usage of promises as we build our Angular 2 application, its very effective.

This brings us to the end of our Typescript journey, though what we've seen above is just a summary of the main parts of Typescript we'll be using in our Angular2 application.  Let's get started with building an app in Angular 2. 



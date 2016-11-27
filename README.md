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
* Text Editors
* Installation and Setup 
	* Nodejs Installation
	* Angular CLI Installation
	* Atom Text Editor Installation
	* Install Typings
	* Install Firebase
	* Install Typscript definitions for Firebase
	* Create New Angular 2 Project
	* Start a server
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

####Installations summary
1.  Download and Install Nodejs from http//nodejs.org
* Open a command prompt (cmd) on your computer by clicking on your start menu and typing (running) `cmd` then hit enter. 
* When the cmd window opens, type `node -v` and hit enter. If it shows you a version of nodejs, then nodejs was correctly installed.
2. Install Angular-CLI
* In your command prompt window, run `npm install -g angular-cli`
3. Create new Angular2 project, 
* First navigate to any folder in your computer you want to create the project in. Mine is on my desktop. So to navigate to my desktop, I'd run `cd C:\Users\dell\Desktop\angular projects`. 
* After which I'd run `ng new angular2-blog` to create new angular2 project I decided to name `angular2-blog`. 

Other things you can install are Firebase and Typings as outlined above. 

## Introduction to ES6/Typescript
Typescript is a new powerful programming language built and maintained by Microsoft, it is a superset of javascript and comes with very powerful features such as static typing and class-based object-oriented programming. Google chose to build Angular2 on Typescript instead of its other alternatives such as babel, atScript and Dart. Angular 2 uses TypeScript because it improves developer productivity because of its types. 
If you prefer to work with javascript instead you can visit Angular2's official documentation section and gain access Angular2 documentation for javascript and [Dart](https://angular.io/docs/dart/latest/index.html) although I wouldn't recommend this.

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
Fat arrow functions in Typescript helps write shorter cleaner functions. Here is a comparison between a function written anonymously and the same function replicated with Typescripts fat arrow.

```
//
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


### Template Strings
This is not specifically Typescript, its more of an ES6 feature but its still worth including here because Angular2 implements it. ES6 gives you the ability to write long or multi-line inline strings which is not possible in the good old ES5 javascript without concatenation. Here is what I mean:

```
//In Javascript 
var variable1 =  'I love Dave Partner\'s '+
                 'blackberry phones that are'+
		 'all good in color';
```
As you can see, we had to use concatenation to join each of the line in order to avoid errors. In Typescript, you'd just need to use back ticks, one at the beginning and one at the end. The back tick key is directly above the tab key on your keyboard. Here is the same code in Typescript:

```
var variable1 =  `I love Dave Partner\'s 
                 blackberry phones that are
		 all good in color`;
```

Here is another more detailed example with data binding:

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
The way we will be using  in this app will be making use of double curly bracelates example `{{ eatery_name }}`, instead of the example we used above `${eatery_name}`.  This enables two-way data binding in Angular 2.

This brings us to the end of our Typescript journey, though what we've seen above is just a summary of the main parts of Typescript we'll be using in our Angular2 application.  Let's continue with building our app in Angular2 while explaining basic concepts. 


## Angular 2 Components
A component in Angular2 is just a combination of `.ts` file that contains a controller class which connect to its own `.html` view file and contains the logic that will be displayed in the view. In Angular2, everything is a component or component based. A component also connects to services NS Angular platform core libraries.  Every component has a decorator.

When we created our Angular2 project above using the Angular-CLI command `ng new angualr-blog`, Angular-CLI also created a default component class for us. The component class is called `App Component`. App component is the root component of every angular2 app. 
Every angular2 component has 4 files. Here is an example of the default app component that comes with new Angular2 files: 

```
/.git
/e2e
/node_modules
/app/
	|-app.component.ts - this is the file that contains the class
	|-app.component.css - this contains the css for styles for the view
	|-app.component.html - this contains the html for view 
	|-app.component.spec.ts - contains some defintions, you wont need to touch this file
```
#### How to create a new component
To create a new component, just run `ng generate component <component name>` or `ng g c <component name>` for short. Since we are creating a blog app, let's create a `posts` component. This posts component will contain the list of blog posts. We'll create more components as we move along. 
Run `ng g c posts`. 
This will create a new `posts` folder inside `/app` and add files to it. Our folder structure will now look like this:
```
/.git
/e2e
/node_modules
/app/
	|-posts/
		|-post.component.ts
		|-post.component.css
		|-post.component.html
		|-post.component.spec.ts
	|-app.component.ts - this is the file that contains the class
	|-app.component.css - this contains the css for styles for the view
	|-app.component.html - this contains the html for view 
	|-app.component.spec.ts - contains some defintions, you wont need to touch this file
```

Nice!

Lets create more components we will be needing, run the following

`ng g c posts-add`
This will create a second `posts-add` component that we'll be using to add new posts to the blog.

#### Parts of a component
An angular 2 component `.ts` file has different parts. We'll explain it using the generated code in `posts-add.component.ts`.

```
//posts-add.component.ts
//import section
import { Component, OnInit } from '@angular/core';


//decorator
@Component({
  selector: 'app-posts-add',
  templateUrl: './posts-add.component.html',
  styleUrls: ['./posts-add.component.css']
})

//class
export class PostsAddComponent implements OnInit {

//constructor
  constructor() {
  	first_name = 'Dave'; //I added this
  }

  ngOnInit() {
  }

}
```

The main sections we will be explaining above are the `import` , `decorator`, `class` and `constructor` sections.

### Imports
The `import` section is always at the top of the page, usually the first in the `.ts` component file. 
Its the section where the component imports all the libraries, services, classes and other components it needs to build the logic for display on the `.html` view file. 

#### Decorator
The `decorator` function of the code defines the meta data for the class immediately below it. Decorators always start with `@` symbol. The decorator above defines the files where the css style and template is located, it also defines the html selector that represents this component. 
Here is a full list of metadata properties that can be defined inside a decorator in Angular2, although we'll eventually be making use of just few key ones in this tutorial. 
Angular2 Metadata Properties:
inputs - list of class property names to data-bind as component inputs
interpolation - custom interpolation markers used in this component's template
moduleId - ES/CommonJS module id of the file in which this component is defined
styleUrls - list of urls to stylesheets to be applied to this component's view
styles - inline-defined styles to be applied to this component's view
template - inline-defined template for the view
animations - list of animations of this component
changeDetection - change detection strategy used by this component
encapsulation - style encapsulation strategy used by this component
entryComponents - list of components that are dynamically inserted into the view of this component
exportAs - name under which the component instance is exported in a template
host - map of class property to host element bindings for events, properties and attributes
templateUrl - url to an external file containing a template for the view
viewProviders - list of providers available to this component and its view children  
outputs - list of class property names that expose output events that others can subscribe to
providers - list of providers available to this component and its children
queries - configure queries that can be injected into the component
selector - css selector that identifies this component in a template

The `class` functions just like a normal class in Java or C#, its just a collection of objects.  The class has a constructor function that runs by default once you the class is instantiated. The class also has an `export` statement that makes sure the class can be `imported` in any other component and used, just like we saw in the `import` section description above.

The  ngOnInit() function fires everytime the component is called. As you can see, `OnInit` is also imported in the importsection from `angular/core`. 
Like so:
`import { Component, OnInit } from '@angular/core';`


#### Two way data binding
Inside the constructor class we declared a variable called `first_name`and assigned the value of `Dave` to it. This variable is also accessible from the `.html` file of a component with no extra effort on your part. That's the power of angular2. 
Let's see what's in the `posts-add.component.html` and how the variable can be used there.

```
//src/app/posts-add/posts-add.component.html
<p>
  posts-add works!
</p>
```
The above is just a basic html, when the component is called, it should just print `post-add works!`. Lets just add the variable we declared in the component class in `posts-add.component.ts`. To do that we just need to put the variable in double curly bracelets `{{first_name}}`
```
//src/app/posts-add/posts-add.component.html
<p>
  {{first_name}} posts-add works!
</p>
```
To inject the code of one `.html` file into another, you have to:
* First: Import the component class int the `.ts` file of the new component you'd like to inject it into. Here is the syntax: 
`import {ClassOfOldComponent} from '<path to where the .ts file is located>';`

* Second: place the html-selector of the old component inside the html of the new component. 
Don't worry, we'll see this in practice as we build a blog.

Since we are building a blog, let's insert the contents of the `posts-add.component.html` into `app.component.html`. This is because `app.component.html` is the default component displayed when you visit your homepage. Your homepage is proabably located at `localhost:4200` when you visit on your browser.


```
srs/app/app.components.ts 
import { Component } from '@angular/core';
import {PostsAddComponent} from './posts-add/posts-add.component'; //I just added this, it just imports posts-add component class into app.component.ts to be used

//the rest of this file goes here
```

Then go to the html and add `<app-posts-add> Loading</app-posts-add>`
```
srs/app/app.components.html
<h1>
Home works!
</h1>

<app-posts-add> Loading</app-posts-add>  <!--here is the selector for posts-add.component.html. The compiler will simply replace <app-posts-add> Loading </app-posts-add> with the html contents in posts-add.components.html -->

```

That's how to use one component into another. You can inject multiple components into others with no limitation. We'll use it as we build a blog further down the book. 


### Adding Custom Assets
#### Twitter Bootstrap To Your Project
Bootstrap is a HTML,CSS and Javascript framework for designing beautiful and responsive user interfaces in web and mobile applications. It makes sense that we use it in this project instead of writing our own custom css from scratch. 
We'll be using [Twitter bootstrap](http://getbootstrap.com) to style our blog to make it beautiful. 
To do this, visit http://getbootstrap.com/getting-started/ , scroll down to the `Bootstrap CDN` section and copy the 3 stylesheet and javascript links there. Then paste it anywhere inbetween the <head> </head> section of your `src/index.html` file. 
Bootstrap also needs Jquery to function properly, so add jquery too by visiting https://code.jquery.com/ . On the page, select 'minified' version of the jquery version you want, then copy the code that pops up. I selected the minified version of Jquery version 3.x . 
Paste the code you copied at the bottom of your `index.html` file, just before the closing `</body>` tag.

Here is mine, pay attention to the comments

```
located at src/index.html
<!doctype html>
<html>
<head>
  <meta charset="utf-8">
  <title>Angular2Blog</title>
  <base href="/">

  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="icon" type="image/x-icon" href="favicon.ico">

  <!-- I added the below -->
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous">
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap-theme.min.css" integrity="sha384-rHyoN1iRsVXV4nD0JutlnGaslCJuC7uwjduW9SVrLvRYooPp2bWYgmgJQIXwl/Sp" crossorigin="anonymous">
  <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js" integrity="sha384-Tc5IQib027qvyjSMfHjOMaLkfuWVxZxUPnCJA7l2mCWNIpG9mGCD8wGNIcPD7Txa" crossorigin="anonymous"></script>

</head>
<body>
  <app-root>Loading...</app-root> <!--this inserts the contents of app.component.html into this index.html page -->
  
  <!--added Jquery too below -->
  <script
  src="https://code.jquery.com/jquery-3.1.1.min.js"
  integrity="sha256-hVVnYaiADRTO2PzUGmuLJr8BLUSjGIZsDYGmIJLv2b8="
  crossorigin="anonymous"></script>
  
</body>
</html>

```

Nice, we are now good to go. We can now start using bootstrap and jquery UI features.  If you do not know how to use bootstrap, you can [checkout my boostrap tutorial on youtube] (https://www.youtube.com/playlist?list=PLnBvgoOXZNCMXAQ3FTgExmqYCzkfKKYDD).

#### Desinging our homepage
You can design your homepage using your usual HTML, CSS and Javascript. Since we are now using bootstrap in the project, I'll just build it all out using boostraps styles and classes. 
Since all all our pages will contain A top navigation bar, lets add it right under the opening `<body>` tag of `src/index.html`. I'll also add a footer. Update the file to look like this:

```
<body>
  <nav class="navbar navbar-inverse navbar-fixed-top">
      <div class="container">
        <div class="navbar-header">

          <a class="navbar-brand" href="#"> <i class="glyphicon glyphicon-list-alt"> </i> Angular2 Blog</a>
        </div>
        <div id="navbar" class="navbar-collapse collapse">
          <form class="navbar-form navbar-right">
            <div class="form-group">
              <input type="text" placeholder="Email" class="form-control">
            </div>
            <div class="form-group">
              <input type="password" placeholder="Password" class="form-control">
            </div>
            <button type="submit" class="btn btn-success">Sign in</button>
          </form>
        </div><!--/.navbar-collapse -->
      </div>
    </nav>

  <app-root>Loading...</app-root> <!--this inserts the contents of app.component.html into this index.html page -->

<!--footer section -->
    <footer>
          <p>&copy; 2016 Company, Inc.</p>
    </footer>
	
  <script
    src="https://code.jquery.com/jquery-3.1.1.min.js"
    integrity="sha256-hVVnYaiADRTO2PzUGmuLJr8BLUSjGIZsDYGmIJLv2b8="
    crossorigin="anonymous"></script>
  <!-- Latest compiled and minified JavaScript -->
  <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js" integrity="sha384-Tc5IQib027qvyjSMfHjOMaLkfuWVxZxUPnCJA7l2mCWNIpG9mGCD8wGNIcPD7Txa" crossorigin="anonymous"></script>

</body>

```

The above will show a blank page with a black top navigation bar and a login form. Next, we head over to `src/app/app.component.ts` and change its content to the following code. 

```
<!-- Main jumbotron for a primary marketing message or call to action -->
   <div class="jumbotron">
     <div class="container">
       <h1>Hello, world!</h1>
       <p>Welcome to our first Angular2 blog. Please find our blog posts below.</p>
       <p><a class="btn btn-primary btn-lg" href="#" role="button">Learn more &raquo;</a></p>
     </div>
   </div>

<div class="container">
  <app-home>Loading...</app-home> <!-- Notice that we are importing the contents of src/app/home/home.components.html here -->
     <hr>

   </div> <!-- /container -->

```

app.component is basically the root component of the application, that is to say, if you stack all the components one on top the other, the app.component will be at the top. 
* Notice that we are importing the contents of `src/app/home/home.components.html`. 

So let's head over to `src/app/home/home.components.html` and insert some code. The code we will insert will be a dummy code that will eventually list the latest blog posts when we connect this application to a database. If you have not created `home.component` you can create it by running `ng g c home` on your cmd. Or you can use the `post component` we created ealier for this purpose. We just need to list the latest posts with a short description each. 
So open `src/app/home/home.components.html` and change the code there to: 

```
<!-- Example row of columns -->
<div class="row">
  <div class="col-md-4">
    <h2>Heading</h2>
    <p>Donec id elit non mi porta gravida at eget metus. Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh, ut fermentum massa justo sit amet risus. Etiam porta sem malesuada magna mollis euismod. Donec sed odio dui. </p>
    <p><a class="btn btn-default" href="#" role="button">View details &raquo;</a></p>
  </div>
  <div class="col-md-4">
    <h2>Heading</h2>
    <p>Donec id elit non mi porta gravida at eget metus. Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh, ut fermentum massa justo sit amet risus. Etiam porta sem malesuada magna mollis euismod. Donec sed odio dui. </p>
    <p><a class="btn btn-default" href="#" role="button">View details &raquo;</a></p>
 </div>
  <div class="col-md-4">
    <h2>Heading</h2>
    <p>Donec sed odio dui. Cras justo odio, dapibus ac facilisis in, egestas eget quam. Vestibulum id ligula porta felis euismod semper. Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh, ut fermentum massa justo sit amet risus.</p>
    <p><a class="btn btn-default" href="#" role="button">View details &raquo;</a></p>
  </div>
</div>
```

That settled, run `ng serve` and view your app on your browser by visiting `localhost:4200` . You should see a beautiful but static blog. 

##Ng-Content Directive
This is a way that Angular2 makes sure that the initial content of your component's selector does not get overwritten when the component's content gets loaded. 
Normally, if you had `<app-home>Loading... </app-home>`. The `loading...` will be replaced by whatever is located in `src/app/home/home.component.html` when it is loaded. If you dont want this replacement to happen, but wish to display both contents at the same time, you'll need to go to `src/app/home/home.component.html` and enter the tag `<ng-content> </ng-content>` at any part of the code you wish the contents of  `<app-home>Loading... </app-home>` to be displayed. 
Its as simple as that - go to the component and tell it where to append the initial contents of its selector. 


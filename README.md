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

###Editors

The first thing you'll need is an environment to write your code. There are many Integrated Developmemt Environments (IDE) you can use. However, the below are the ones I use.  

 * Your current IDE. If you have ever written any HTML code then you can keep using that IDE you used to write the code.
 * [Notepad++](https://notepad-plus-plus.org/download/v7.2.html) - This is lightweight, simple and will get the job done. 
 * [Sublime Text ](https://www.sublimetext.com/download) - Really superb, lightweight and smart too.
 * [Aptana Studio 3](http://aptana.com/) 
 * [Atom.io](https://atom.io/) - This is my new found love, it has really powerful features to make your code easy. I combine it with codelobster, link below.
 * [CodeLobster](http://www.codelobster.com/download.html) - I really like this code editor when ever I am write html, css and javascript codes because of its amazing syntax highlighting and code folding that comes as default settings.
You just need one of the above listed IDEs. 

There are many others [listed here](http://en.wikipedia.org/wiki/List_of_HTML_editors), you can check them out.

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



Simple enough!  Now, we've looked at the `style` attribute a bit now but I haven't explained the syntax.  The `style` attribute is for *inline styles*.  This means that you're styling your HTML directly in each element, rather than using CSS.  But, we haven't gotten that far yet, so I won't go into that part.

Now, the syntax within a `style` attribute is a little funky.  It is always `style="property: value"`, where the *property* is literally a property of the tag you're editing (for example, `color`, `width`, `height`), and the *value* is to what you're changing or editing the property (for example `blue`, `600px`, `#FF0000`).
If you have more than one property that you want to style, for example both height and width, you put a semicolon between delarations.  So, in our example, if you want to edit both height and width of our image in the `style` attribute, we'd do:

	<img src="http://i.imgur.com/wjiVXJe.gif" style="width: 600px; height: 800px" />
	
Why is the syntax this funky?  Well, that's because it's secretly CSS syntax.  But we'll get into that more later.

####Borders

What if we have a paragraph IN A BOX.  That's right.  Kind of like a table.  But not.  That'd be cool.  Of course, there are plenty of other things that can have a border.  Buttons (we'll get to those later), color blocks (also later), and images, and MORE can have them.  Mmmhm.

Let's take the same image we played with before:

	<img src="http://i.imgur.com/wjiVXJe.gif" />

Now, you can add `border="5"` to this and you'll get a border with a thickness of 5 pixels around the image.  But, this attribute is actually no longer supported for things other than tables (oh yeah, we used this for tables.  Memories.), so we can do this a better way.  You guessed it. `style` is coming to SAVE THE DAY.

The styling for borders with the `style` attribute is a bit different than just adding `border="5"`, but it's also much more powerful.  Let's change our code:

	<img src="http://i.imgur.com/wjiVXJe.gif" style="border:5px solid black" />

Whoa.  That's a lot of crap in there.  Let's break it down.

The first part of the declaration is obvious, `border`.  This is the property that we're editing.  Man, this is easy.

Next, we have 3 parts in the value section.  The first part is `5px`.  Firstly, `px` stands for *pixels*.  We used this above for our width and heights as well.  You always have to include the units (just like in 5th grade math) in your styling, and our units here are pixels.  Now, that whole first part, `5px`, is the border's thickness.  You guessed it: it's 5 pixels thick.  Gosh you're smart.
The next part is the *border style*.  You can plug in several words here, as indicated [on this webpage](http://www.w3schools.com/css/css_border.asp).  We used `solid`, but you can also say `dotted`, `dashed`, or `double`.  There are some other words you can use, but those depend on the color of the border.  
Color?  What?  OH YEAH.  That's the third part of the border style.  You can stick in any color for that, but in this example, we have `black`.

Let's mix it up a bit with different borders for you to check out.  I'm just going to keep using the same image, you can replace it with whatever.  Stick this in the `<body>` tags of style1.html and check it out, and play with the values yourself!

	<img src="http://i.imgur.com/wjiVXJe.gif" style="border:5px dotted #ffcc00" />
	<img src="http://i.imgur.com/wjiVXJe.gif" style="border:10px ridge rgb(77, 145, 99); width: 300px" />
	<img src="http://i.imgur.com/wjiVXJe.gif" style="border:8px outset red" />	
	<img src="http://i.imgur.com/wjiVXJe.gif" style="border:3px double #333a21; height: 30px" />
			
			
Notice how I added `width` and `height` to a couple of them.  We're getting incestuous with our stylings.  Aww yeah.

####Text Styles

Besides having header tags and colors, there are other text styles that you can use.  What if you want bold text, or italics?  Different sizes?  Once again, the `style` attribute comes to the rescue.

Add the following to style1.html in **3 - Styles**:
	
	<p style="text-align: center; font-weight: bold">This text is magnificent.</p>

Load that in a browser and check it out.  YUS.  You've got some magically centered, bolded text!  The properties defined here are pretty simple to follow.  `text-align` lets you align your text either `center`, `left`, or `right`.  Mess around with that so you get it.
`font-weight`, you guessed it, edits the weight in your text.  It can have the values `normal` for normally weighted text, `bold` for thick characters, `bolder` for thicker characters (specific, right?), `lighter` for lighter-weighted characters, and the numbers `100`, `200`, `300`, `400`, `500`, `600`, `700`, `800`, and `900` (where 400 is the same as normal and 700 is the same as bold).

Play with this one now:
	
	<p style="font-family: Arial; font-style: italic">This text is magnificent.</p>
	
Browser time.  You've now got some text in the font Arial, and it's italic!  WOOO HOOOOOO.  
The properties we used here are `font-family` and `font-style`.  For the former, you can choose a lot of fonts, but you have to be careful.  Not every computer has the same fonts.  This is just my personal opinion: don't put something here besides Arial unless you've done some JavaScript magic.  And because I'm assuming you don't know JavaScript, don't use this unless you're changing this to Arial.  At least not yet. :)
And for `font-style`, it can be `normal`, `oblique`, and `italic`.  You can play with those now, it's pretty straightforward.

###The `<head>` Tag

Before we start going insane with how good you are at HTML, let's start looking at something that you haven't played with yet.  The `<head>` tag.

I mentioned before that in the `<head>` is information that the user doesn't see, so it's not that big of a deal, right?  WRONG.  It's not all about looks.  That's at least what I try to tell people when they see me.

So.  What else can go in the `<head>`?  We've already got `<title>`, which we've talked about already to help search engines find us.  What if we want to help the search engines out a bit more?  Incoming, the `<meta>` tag.

The `<meta>` tag gives *metadata* about the HTML document. Metadata will not be displayed on the page, but machines can read it.  An example of metadata not on a webpage is in a typical music file.  When you have a music file on your computer and you open it in some media player of some kind, it shows the album title, the artist, the genre, and other information about the song.  This information is metadata.  The user can't see it directly in the music file, but your music players can read it and will tell you what it is.
So, on a website, this metadata is used by search engines, your browser, and other web services to make your website easy to find, read, and display.

There are 4 important uses for the `<meta>` tag.  There are plenty of other uses, but let's be honest, I don't care about them right now, and I don't think you do either.
Open up the **4 - Head** (heh get it?  Forehead?  I crack myself up.) folder, and open cooking.html in your favorite editor.

 * *Defining keywords for search engines.*  Let's say that you have a website that's about cooking, hence our filename.  You want people searching for your website to be able to find it.  So, you can add the following right before the `<title>` tag:

`<meta name="keywords" content="cooking, cook, recipe, food, microwave">`
	
Simple enough.  Now, when people search using the terms cooking, cook, recipe, food, and microwave, your website is pushed up in the results.  Nice!
	
 * *Defining a description of your site.*  Again, this one is for the search engines.  Whenever you search for a website, there's a tiny description in the search results.  Go search for anything right now, and you'll see it.  So, you can define what that is with this snippet:

`<meta name="description" content="The best cooking website in the entire universe.  You're welcome.">`

Add this right after the keywords line in cooking.html.  Now if people were searching for this, they'd get this description and instantly see that your website is the best cooking website in the universe.

 * *Defining the author of a website.*  Let's say that someone's looking for the author of your website, because your writing style is sexy.  Or something.  You can let them know who you are with the following:

`<meta name="author" content="Sexy McGoodlooking">`
	
Add this after your description line, and stick your name in it!  I think I got it as close as possible.

 * *Refreshing your document every 30 seconds.* This one is for your browser.  Let's say that you have comments available on your recipes, and you want to have the page refresh so the comments can appear "live".  Just add this:

`<meta http-equiv="refresh" content="30">`
	
And there you have it, a self-refreshing webpage.  You're so good at this.

###Putting it all together so far

Okay, you have a pretty solid understanding of stuff so far.  I want you to take cooking.html, and make it shine.
Resize the images so the page is more uniform.  Add borders to them.  Change the font styles and weights.  Change the colors.  Add some keywords in the metadata and change the title of the page.
Using the information I've given you so far, you can make a pretty good looking site!

##CSS is magical, and now you're gonna learn it.

So far, we've been making things pretty the wrong way.  So, we're going to learn it the right way.  So excited.

Right now, I'm going to show you how to write CSS just straight in your HTML documents.  That's still kind of wrong, but it'll give you the basics.  After that, we'll move into the big leagues and have separate files for everything.  Pumped.  

Open up your **3 - Styles** folder again and open style2.html in your favorite editor.  This site is pretty barebones.  Let's take out the barebones part and just make it pretty.

We're going to be working in the `<head>` tag again.  Underneath the `<title>` tag, stick in the following:

	<style>
		body
		{ }
		
		h1
		{ }
		
		p
		{ }
		
		ol
		{ }
	</style>
	
Congratulations.  You have some empty CSS.  Now, what the heck is CSS anyway?  Well, CSS stands for *Cascading Style Sheets*.  Gee whiz, that word *style* is everywhere.  And it's true.  The `style` attribute is for styling *inline* HTML (just that line of code), the `<style>` tag is for holding CSS, and CSS *defines* the styles!  Let that sink in.  Nice.  Stylish.  Just like you.

Now, you'll notice some familiar keywords in there, in particular, `body`, `h1`, `p`, and `ol`.  That's right, they're the tags we know and love!  But, in CSS, these are called *selectors*.  The selector tells us what tag you're about to style.  So, whatever code you put in between the curly braces `{}` after the `body` selector will affect everything in the `<body>` tags.  Whatever you put in the braces after the `p` selector will affect what's in the `<p>` tags.
Whatever code you have in those curly braces will only affect that tag, so if you try editing the font colors for the `h1` selector, it won't affect whatever is in the `p` selector's tags.  Each portion of code `selector { code }` in CSS is called a *declaration*.  Make sense?  Good.  If not, keep reading and hopefully it will become more clear as we go on.

The code that we're going to be putting in each declaration is the same syntax as the code that we normally put in the `style` attribute.  How convenient.  So, change your code above to the following:

	<style>
		body
		{
			font-family: Arial;
		}
		
		h1
		{
			color: red;
			text-align: center;
		}
		
		p
		{
			font-weight: bolder;
		}
		
		img
		{
			width: 400px;
			border: 5px solid #333333;
		}
		
		ol
		{
			color: #333333;
		}
	</style>

Recognize that?  It's exactly the same!  For each selector, there is a *property* of that selector, and each property has a *value*, just like how we wrote it in the `style` attributes!

You will always have your CSS in the syntax, `selector { property: value; property: value; }`.  I've only shown you some properties so far, but don't worry.  There are plenty more to come.

Try playing around with the CSS we have right now.  Edit the colors, add some borders, change the font styles.  Don't forget your semicolons!

###Classes and IDs and other Segregation

So, you have some of the CSS basics down already.  You're so smart.  It's really a simple language, once you know the basic syntax.  So, now we'll get into more fancy stuff.  What if you want to edit several tags differently?

####Classes

Let's say that we have 8 `<p>` tags on our HTML page (hint: open style3.html in the **3 - Styles** folder).  
If we want to style each of these tags differently, we can use *classes*.  A class is actually an HTML attribute that you can name whatever you want.  
Check out style3.html to see the classes I added to the `<p>` tags on the page.  When you add a class, the user doesn't see it.  
But, you can style specific classes to do what you want, instead of having all `<p>` tags be the same.

How about we style one of the classes specifically?  It's simple.  Just take the class name you made up (I'll use the `poemtitle` class for my example) and add a period `.` in front of it to select it in CSS, like so:

	.poemtitle
	{
	
	}

And there you have it!  Even though you might have different styles for your paragraphs, you can style the ones of class `poemtitle` individually.  
For this example, let's make all paragraphs with the font family Arial, the `poemtitle`s font weight `bolder`, the `author`s the color `#555555`, and the `poem`s in `italic`.  
Try doing it on your own if you can (just put your code in the given `<style>` tags), but you're welcome to cheat:

	p
	{
		font-family: Arial;
	}
	.poemtitle
	{
		font-weight: bolder;
	}
	.author
	{
		color: #555555;
	}
	.poem
	{
		font-style: italic;
	}
	
Gosh you're good at this.  Go eat a cookie.

[Pausing here for cookie break]

####IDs

Now, let's talk about IDs.  They are very similar to classes.  The only real difference between classes and IDs is that you can only have one of each ID.  So, for example, if you have a special paragraph that you only want to style once, then you can stick in there the `id` attribute like so:

	<p id="special">This is so special that I want it uniquely styled forever.</p>
	
When you want to style your IDs, you put a hashtag `#` before it in your CSS, like so:
	
	#special
	{
	
	}
	
Remember:  You can only use an ID once.  IDs are more helpful when you're controlling the element with JavaScript, not styling, but that's something for another day.

####Other Segregation

Let's say that you want to separate individual text in your paragraphs or sections on your page.  Let's introduce 2 new tags: `<span>` and `<div>`.

#####The `<span>` tag
The `<span>` tag is pretty invisible unless you style it.  It's used to group *inline-elements* (so like a word in a paragraph), and it doesn't actually do anything unless you style or manipulate it with something else.

So, let's say you have a paragraph and you really want to emphasize some text within a paragraph without a line break or anything.  In comes `<span>`.  For example:

	<p>"My grandmother started walking <span>five miles a day</span> when she was sixty. She's ninety-seven now, and <span>we don't know where the heck she is.</span>" </p>
	<p>~ Ellen DeGeneres </p>
	
In the above quote, you might want to style the `<span>` tags differently than the rest of the paragraph.  Maybe you want those words bold, or italics, or in red.  Now you can.

Add some `<span>` tags around your favorite lines of the poems in style3.html of the **3 - Styles** folder.  Then, put the following CSS in your `<style>` tags:
	
	p span
	{
		font-style: italic;
	}

Wait a minute.  Hold up.  `p span`??  WHY THE SPACE?  Calm yourself, I'll tell you.  This is called *nesting* CSS.  When you have a space in your selector like this, it means that, in this case, the style will only affect `<span>` tags within `<p>` tags.  So, if you put `<span>` tags around a word in your `<h1>` tags, your CSS will not affect it.  You can still have a plain `span` selector, or nest it in one of your classes too:

	span
	{
		font-weight: bold;
	}
	.author span
	{
		color: #999999;
	}

Make sense?  I hope so.  To sum up: `<span>` tags separate specific parts of paragraphs or other inline sections of a page.  They do nothing otherwise.  You can nest CSS if you want.  Boom.  Next.

#####The `<div>` tag

Alrighty.  Go enjoy a beach vacation and then come back to this.

Welcome back.

The `<div>` tag is very similar to the `<span>` tag, in that it separates a section of something but doesn't do much else.  However, the difference with `<div>` tags is that they are *block level* elements, not just within a line of text.

The `<div>` tag might end up being the tag that you use most often.  It is what lets you easily make website layouts (with help from CSS of course), and so, let's play with it!

Open up the **5 - Layout** folder, and use your editor to open `homepage.html`.

	<!doctype html>
	<html>
		<head>
			<title> My Website </title>
			<style>
				
			</style>
		</head>
		<body>
			<div class="header"></div>
			<div class="menu"></div>
			<div class="content"></div>
			<div class="footer"></div>
		</body>
	</html>

Besides the `<div>` tags, everything here should look familiar.  Each of the `<divs>` have a `class`, which means we should style those, right?  Right.

Within those `<style>` tags, let's add some pizzazz.  
First, let's throw in what we'll be styling: the `<html>` (it is unusual to style this, but I'll explain why we are later), `<body>`, and each of the 4 classes:

	html
	{
		
	}
	body
	{
	
	}
	.header
	{
	
	}
	.menu
	{
	
	}
	.content
	{
	
	}
	.footer
	{
	
	}

This should be straightforward for you so far.  The first thing we'll do is create our layout by making each `<div>` a different size.

	html
	{
		height: 100%;
	}
	body
	{
		height: 100%;
	}
	.header
	{
		width: 100%;
		height: 60px;
	}
	.menu
	{
		height: 100%;
		width: 15%;
	}
	.content
	{
		height: 200px;
	}
	.footer
	{
		height: 60px;
		width: 100%;
	}

Whoa ho ho, slow down there.  What the heck is with these `%` signs??  Well, what this means is that if, for example, a tag's `width` is `75%`, then it's width on the page will be 75% of it's *containing element.*
So when you see that the `.menu` class has a `width: 15%;`, it takes up 15% of its containing element's width, which is the `<body>` tag.

Typically, the `height` property defaults to `0%` and the `width` property defaults to `100%`.  
This is why we had to style the `height` properties of both `<html>` and `<body>`.
If we had just made our `.menu` selector have a height of `100%`, we know that 100% of zero is just zero, so we wouldn't have a menu showing up!  
When we made the `<body>` tag have `height: 100%`, it also would still be zero, because our `<html>` tag also had a height of 0 without the CSS helping it out.
Now, if we had just said `height: 50px;` for `.menu`, we wouldn't need the `height` fixes for `<html>` and `<body>`, because it's given a set value, not a value dependent on others.  
Makes sense?  I hope so.  You're hot.

Okay, so if you open `homepage.html` in the browser, you see nothing.  That's okay.  Let's change that by learning a few new CSS properties! 

######Background color

One property that you will learn to know and love is `background-color`.  
It does exactly what you would expect it to: it sets the background color of the element it is styling!  
You can fill it in with HEX colors or RGB colors, just like we learned earlier, and the default color is white.

Let's add some backgrounds.

	html
	{
		height: 100%;
	}
	body
	{
		height: 100%;
	}
	.header
	{
		background-color: #99B5DD;
		width: 100%;
		height: 60px;
	}
	.menu
	{
		background-color: #DE90B1;
		height: 100%;
		width: 15%;
	}
	.content
	{
		height: 200px;
	}
	.footer
	{
		background-color: #0F215D;
		height: 60px;
		width: 100%;
	}

Save in your editor and now refresh in that browser!  WOW.  COLOR.  Now, our site definitely isn't perfect yet.  
Let's throw some MORE new CSS properties at you!

######Floating

One property that you will probably use fairly often is `float`.  This is one of those properties that you will learn to both love and hate. 
It's kind of magical.
So, let's say that you want to have a picture in a paragraph.  When you see a picture in a news article or even a paper you're writing, the picture is either on the left or the right.  
It's the same in CSS!  If you wanted to put a picture in a paragraph, you'd make the `<img>` tag inside a `<p>` tag have the properties `float: left;` or `float: right;`.
So, what does this have to do with `<div>` tags?  Why could you potentially hate it?

I'll tell you.

With CSS float, a given element can be pushed to the left or right, allowing other elements to wrap around it.  
An element with `float` affecting it will move as far to the left or right as it can.  
Usually this means all the way to the left or right of the containing element.

Pretty simple, right?  Right.  Now, here's the cause for hate: sometimes, `float` just doesn't stop.  
It has the potential to mess up your layouts and have things move around other things, and really just give you a headache. 
How do you stop that?

With the `clear` property!  On the element(s) after any floated elements, make sure that they have `clear: both;` on them (we say `both` because it turns off both `left` and `right` floating).  
Let's add `float: left;` to the `.menu` and `.content` sections, and `clear: both;` to the `.footer`:

	html
	{
		height: 100%;
	}
	body
	{
		height: 100%;
	}
	.header
	{
		background-color: #99B5DD;
		width: 100%;
		height: 60px;
	}
	.menu
	{
		background-color: #DE90B1;
		height: 100%;
		width: 15%;
		float: left;
	}
	.content
	{
		height: 200px;
		float: left;
	}
	.footer
	{
		background-color: #0F215D;
		height: 60px;
		width: 100%;
		clear: both;
	}

Now if you refresh your browser, things are starting to look a bit more sexy.  Like you.

Let's add more delight to this!  So let's think, what if you're on your website, but you want to see the footer.  
You scroll down.  What if, though, you want to see the header again?  You'd have to scroll back up.

That's exhausting.

Your poor finger.

Let's make it so that your header and footer are always on the top and bottom of your screen, and only your content moves!

Incoming, the `position` property.

######Positioning

The `position` property is pretty much exactly what one would expect a positioning property to do:  It positions things.

It can have several states, but we'll focus on the 3 states you'll probably use most: `absolute`, `relative`, and `fixed` (the default state is `static`, but you will rarely need to work with this).
 * In `absolute` positioning, the selected element will be placed in an exact location on the page, and moves with the page.  So, in our example, the header could be placed at the top of the page and the footer at the bottom, but when you scroll, they will move with the page and they won't stay where they are supposed to.  Some people like this, some don't.  In our case, we won't use this.
 * In `relative` positioning, the selected element will be placed *relative* (fancy that) to its default position.  I'll show you an example of this later.
 * Now, `fixed` positioning is just like `absolute` positioning, except that once an element is placed in an exact location on the page, it is stuck there.  A similar example is like a watermark on a video.  It stays the same there, no matter what the content is.

How do we actually position things after you use `position`?  You can use `top`, `bottom`, `left`, and `right` to place it.
So, for example, if you want a header bar to be at the top of the page (but it's okay if it scrolls with the page), you'll have `position: absolute;` and `top: 0px;` because you want it to be 0 pixels from the top.
If you have an image on your page that's sitting on the left of your document, but it's way too far left, you can do `position: relative;` and `left: 5px` to scoot it 5 pixels to the right (because you're adding space to the left).
Another more complicated example could be if, say, you want a 50px by 50px image to stay in the bottom right corner of your page as you scroll, you could do `position: fixed;` and `right: 50px;` and `bottom: 50px`.  You'll understand it more as we use it!

So, let's get rid of our `float` on `.menu` and `.content`, and the `clear` on the footer.  Let's position everything using `position` instead, like so:

	html
	{
		height: 100%;
	}
	body
	{
		height: 100%;
	}
	.header
	{
		background-color: #99B5DD;
		position: fixed;
		top: 0px;
		width: 100%;
		height: 60px;
	}
	.menu
	{
		background-color: #DE90B1;
		height: 100%;
		width: 15%;
		position: fixed;
		left: 0px;
		top: 60px;
	}
	.content
	{
		height: 200px;
		position: absolute;
		top: 60px;
		left: 15%;
	}
	.footer
	{
		background-color: #0F215D;
		position: fixed;
		bottom: 0px;
		height: 60px;
		width: 100%;
	}
	
We are starting to look really hot now.  
If you refresh your page in the browser though, you'll notice that there's a little space to the left of our header and footer.  
Why the heck is that happening?

I'll tell you.

######Margins and Padding

![Alt](cpbm.jpg)

I made the diagram above to show you what the heck you'll be working with.

First, let's look at the CSS property `margin`.  Like you can see above, `margin` is the space *outside* the content's border.  
Think of it as the 1 inch margins when you write a paper, or the margins of the pages of a book.

The HTML `<body>` tag actually has a natural margin, which is why our header and footer have the space on their sides.  S
o, let's add `margin: 0px;` to our `<body>` (that's all we'll change right now though):

	body
	{
		height: 100%;
		margin: 0px;
	}

Now, let's talk about `padding`.  Padding is the space *inside* the content's border.  Now, if you look at our `.content` currently, it is uncomfortably close to our `.menu`.  These things are not meant to be touching.  I would insert a joke here but you can figure out what the punchline would be.

Anyway.

Let's add some padding into our `.content` and `.header` so that our text has some breathing room.  Our CSS should look like this now:

	html
	{
		height: 100%;
	}
	body
	{
		height: 100%;
		margin: 0px;
	}
	.header
	{
		background-color: #99B5DD;
		position: fixed;
		top: 0px;
		width: 100%;
		height: 60px;
		padding: 10px;
	}
	.menu
	{
		background-color: #DE90B1;
		height: 100%;
		width: 15%;
		position: fixed;
		left: 0px;
		top: 60px;
		padding: 10px;
	}
	.content
	{
		height: 200px;
		position: absolute;
		top: 60px;
		left: 15%;
	}
	.footer
	{
		background-color: #0F215D;
		position: fixed;
		bottom: 0px;
		height: 60px;
		width: 100%;
	}
	
Oh darn!  Did you see how our header expanded?  If you did this right, our header is now starting to overlap the menu and content.  Crap.

There is a way to fix this.

So, instead of adding space to margins and padding on all four sides, you can add them just to the top, bottom, left, and/or right.  There's a few ways to do this:

 * `margin: 5px 10px 15px 0px;`
     * top margin is 5px
     * right margin is 10px
     * bottom margin is 15px
     * left margin is 0px
 * `margin: 15px 0px 5px;`
     * top margin is 15px
     * right and left margins are 0px
     * bottom margin is 5px
 * `margin: 5px 10px;`
     * top and bottom margins are 5px
     * right and left margins are 10px
 * `margin: 15px;`
     * all four margins are 15px
 
The same goes for `padding`, you can also do `padding: 5px 10px 15px 0px;`, etc. for all of the properties above.  We're going to make some changes to both the `.header` and the `.menu` here:

	html
	{
		height: 100%;
	}
	body
	{
		height: 100%;
		margin: 0px;
	}
	.header
	{
		background-color: #99B5DD;
		position: fixed;
		top: 0px;
		width: 100%;
		height: 60px;
		padding: 0px 10px;
	}
	.menu
	{
		background-color: #DE90B1;
		height: 100%;
		width: 15%;
		position: fixed;
		left: 0px;
		top: 60px;
		padding: 10px 0px 0px;
	}
	.content
	{
		height: 200px;
		position: absolute;
		top: 60px;
		left: 15%;
		padding: 10px;
	}
	.footer
	{
		background-color: #0F215D;
		position: fixed;
		bottom: 0px;
		height: 60px;
		width: 100%;
	}

Now, with all that you've learned so far, you should probably make this a really great, functional website.  
I'll teach you just one more thing, and then I'll set you free like a bird or something.

######Z-Index

The property `z-index` isn't one that you'll run into super often, but it's something that will help you in the long run. 

Now, if you think of your screen as a stack of layers, like a stack of paper on the screen.  
Layer 1 is the lowest layer, and the higher the number, the higher the layer.

The numbers in `z-index` are the same.  If an element has `z-index: 0;`, then it is a bottom layer.  
If you have an element with a `z-index: 5;`, it's going to be on the 5th layer.

When you create a page and you don't add `z-index` to anything, the layers are just in order.  
So in our example, the `.header` was created first, so it's on the lowest layer, and the `.footer` was created last so it is on the top layer.

We don't want that.  What if your `.content` had a ton of information and you had to scroll the page?  
The content would overlap on top of the header (because we just HAD to make our header `fixed`).

So, let's add some `z-index` magic to our page!  A couple things to note first:

 * `z-index` only works when you have already set the `position` of an element.
 * You can assign any number you want to `z-index`, as long as it is an integer (no decimals), and as long as the highest number is the highest level, and the lowest number is the lowest level.

Okay, I'm going to add some `z-index` properties to the page, and I'm also going to add some text changes that you have seen before (`text-align`, `font-family`) and one that you haven't seen before (`font-size`... you get one guess to figure out what this does):

	html
	{
		height: 100%;
	}
	body
	{
		font-family: Arial;
		height: 100%;
		margin: 0px;
	}
	.header
	{
		background-color: #99B5DD;
		position: fixed;
		top: 0px;
		width: 100%;
		height: 60px;
		padding: 0px 10px;
		font-size: 50px;
		z-index: 10;
	}
	.menu
	{
		background-color: #DE90B1;
		height: 100%;
		width: 15%;
		position: fixed;
		left: 0px;
		top: 60px;
		padding: 10px 0px 0px;
		text-align: center;
		z-index: 5;
	}
	.content
	{
		height: 200px;
		position: absolute;
		top: 60px;
		left: 15%;
		padding: 10px;
		z-index: 0;
	}
	.footer
	{
		background-color: #0F215D;
		position: fixed;
		bottom: 0px;
		height: 60px;
		width: 100%;
		z-index: 10;
	}

And there you have it!  Look at your website in your browser and feel proud of yourself.  Eat some cake.  Do a dance.  

Now you can see how flexible `<div>` tags really are.  You can style them pretty much any different way you want without breaking a sweat.

So, you have this delightful homepage set up now, try adding some content and play with the CSS a bit to make it your own!  Add colors, change sizes, the works.
When you click on the links to the other pages, About and Contact, you'll notice that they have no style right now (unlike you).  Change that!  Try making your own layout for each of those pages.  If you're really digging what we've made here, that's cool too.  You can copy over the styles to each page.

But hey, that's a LOT of reusing code.  Plus what if someone is trying to read your code, and they don't get what you're doing (because they aren't as smart as you are)?  Is there a better way?

Duh.

###The `<link>` Tag, Comments, and other Developer Joys

Let's just say you want to reuse your styles across your website on every page.  It makes sense.  
It'd be kind of annoying to have drastic changes on every page.

####The `<link>` tag

That's where the `<link>` tag comes in!  The `<link>` tag is an empty tag (like <br> and <img>), so it has no end tag, and it's used to link to external stylesheets!

What the heck is an external stylesheet?  Well, put simply, it's CSS, in its own file.

You write the `<link>` tag like this:

	<link rel="stylesheet" type="text/css" href="main.css">

Let's take a look at those attributes.  The `rel` attribute is for *relationship*.  
It specifies the relationship between the current document and the linked document, which will almost always be `stylesheet`.  
I've never actually seen it in action with anything other than `stylesheet`, but if you really want to know other values you can look it up.
The `type` attribute will also pretty much always be `text/css`.  If it's ever anything else when you want to use it with CSS, I will be quite surprised.
And finally, `href`.  You remember this one, I hope!  It's just like our `<a>` tag.  It is the URL of the stylesheet.

Let's check out this `<link>` tag in action.  Open up the **6 - Linking** folder and open home.html, and paste the `<link>` line above on the line below the `<title>` tags in the `<head>`.  Voila!  That's it.  Refresh your browser and check out the magic.  It should look just like what we made in the previous section!  
Now, if you open the main.css file in your editor, you'll see that it's all the CSS you recognize and love, but there's no `<style>` tags.  Those tags aren't needed when you are using a CSS file!

####Commenting

Let's just say that you want to show off your code to someone, but they're not exactly sure what you're doing.  

You can add comments!

*Comments* in your code are blocks of text that will not be read by the computer.  Every computer language has them.

#####HTML Comments

In HTML, a comment looks like this:

	<!-- This is an HTML comment! -->

As you can see, it almost looks like a regular tag, with an opening `<!--` and an ending `-->`.  You can put this pretty much anywhere in your HTML files and it won't affect your work!

Look inside the **7 - Project** folder, and open index.html.  You'll see a few comments there.  Notice how you can put them all on one line, or in a multi-line block!  As long as you have a beginning `<!--` and end `-->`, you have total freedom with comments.

#####CSS Comments

Don't worry, you can comment your CSS too!

A comment in CSS is similar to HTML in that it has a beginning and end part, but it looks a little different:

	/* This is a comment in CSS! */

Just like in the HTML comments, you have a beginning `/*` and an end `*/`.  
If you open up main.css in the **7 - Project** folder, you can see the comments I wrote in there!  
And again, you can have single-line comments, and multi-line ones too.

Comments are great for keeping track of what you're doing, especially if a project you're working on spans over a period of time.  
You can make notes for yourself to check later, or you could just tell someone who is reading your code that they are attractive.

####Other Developer Joys

There's so many things that could go in this section for such a generic title.  So, what am I going to tell you?  
Well, I'm going to tell you what I *haven't* taught you so far.

#####Forms

A common thing you'll see on websites are forms, like textboxes, buttons, and checkboxes.
I didn't teach you these because you can't do things with them unless you know a bit more than beginner knowledge, which isn't the purpose of this tutorial.

If you're really dying to see a button, here you go:

	<button type="button">Click Me!</button>
	
And there you have it, a button on your website!  If you actually want to know how to make the button or form do something, you'll need to know some JavaScript.
Until you do, here's more information on buttons: [W3Schools - HTML Forms](http://www.w3schools.com/tags/tag_form.asp)

#####HTML5 and CSS3

If you've read anything about the internet and developing for it, you've probably heard some key words thrown around, and a couple of those key words are HTML5 and CSS3.
What are those, actually?  Well, HTML5 is the latest standard for HTML.  The previous HTML version came out in 1999, which is quite a while ago.  Unless you're time traveling right now and you printed this out to read as you go.

Anyway.  HTML5 was designed to deliver rich content without the need for additional plugins (for example, Shockwave Flash, Silverlight, etc.), and can handle everything from animation to graphics, music to movies, and can also be used to build complex web applications. 
Not to mention the fact that it works on every device, from tablets to phones to your standard computer.

CSS3 has a bunch of new features too.  From new selectors to fancy text effects to 2D/3D tranformations, there's just so much to learn!

If you want to read more about HTML5 and CSS3, check out some of the links below.  If you feel like you've mastered the materials you learned here, you're probably ready to start diving in further!

 * [W3Schools - HTML5](http://www.w3schools.com/html/html5_intro.asp)
 * [W3Schools - CSS3](http://www.w3schools.com/css/css3_intro.asp)
 * [HTML5 Rocks](http://www.html5rocks.com/)
 * [Dive Into HTML5](http://diveintohtml5.info/)

#####How To Meet Ladies/Laddies (Get it? HTML Jokes are the best...)

Honestly I have nothing to put here I just like the joke that HTML stands for that.

I hope your HTML is spick and `<span>`.  Heh.

##Final Project!

Alrighty!  So you've looked at the **7 - Project** folder a bit, but I haven't told you what that folder is for yet.

Well guess what.

It's a project. [confetti]

With all that you've learned so far, make something!  I want you to make a website about the most attractive person in the room.

You.

Put a photo up of yourself, add a biography, talk about your skills (be sure to include HTML and CSS among them) and experiences, make it the online version of you.

Use `<div>` tags and CSS to make a really awesome layout.  Style everything in the text from `<h1>` to `<p>`.  

Include lists `<ul>` and links `<a>`!  Make it sparkly.

I made your homepage for you, and your main CSS document.  But don't let that limit you!  Add as much as you want, and experiment!

The best way to learn is by doing.  Do as much as you can until you think you have everything down pat.

And if you need help you can always come back and visit. :)

##And now, the end is near

Actually, now the end is here.

You've learned pretty much all that I can teach you.  Congratulations, really.  I'm not even going to joke around here.
You've accomplished something that will help you for years to come!

Show off your website to your friends, and be proud of what you've done!  

And with that, I'm signing off.

Thanks for reading, you beautiful specimen, you.













 

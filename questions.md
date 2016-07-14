##JS
- Explain event delegation
With event delegation, we're able to add an event listener to the parent element and target any children elements that way. This saves us from having to add/remove event listeners if children elements are frequently added or deleted. A shortfall of this is if you're adding an element to the list via a script/jQuery - the event listener won't be attached to it (after the fact).
- Explain how this works in JavaScript
- Explain how prototypal inheritance works
- What do you think of AMD vs CommonJS?
- Explain why the following doesn't work as an IIFE: function foo(){ }();.
  - What needs to be changed to properly make it an IIFE?
it should be this: (function foo(){ })();
IIFE's are wrapped in parens
- What's the difference between a variable that is: null, undefined or undeclared?
  - How would you go about checking for any of these states?
- What is a closure, and how/why would you use one?
- What's a typical use case for anonymous functions?
- How do you organize your code? (module pattern, classical inheritance?)
- What's the difference between host objects and native objects?
- Difference between: function Person(){}, var person = Person(), and var person = new Person()?
- What's the difference between .call and .apply?
- Explain Function.prototype.bind.
- When would you use document.write()?
- What's the difference between feature detection, feature inference, and using the UA string?
- Explain Ajax in as much detail as possible.
- What are the advantages and disadvantages of using Ajax?
- Explain how JSONP works (and how it's not really Ajax).
- Have you ever used JavaScript templating?
  - If so, what libraries have you used?
- Explain "hoisting".
Hoisting refers to functions in the global scope (declared or expression) that are able to be executed even when defined below the call. JS parses through a script file first to find the functions, "hoists" them to the top, and then parses through the code on a second run.
- Describe event bubbling.
- What's the difference between an "attribute" and a "property"?
- Why is extending built-in JavaScript objects not a good idea?
- Difference between document load event and document DOMContentLoaded event?
- What is the difference between == and ===?
== allows for type conversion, i.e. 0 == false and 1 == "1" both qualify as true. However, in each instance if you used === they would be false
- Explain the same-origin policy with regards to JavaScript.
- Make this work:
```js
duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]
```
- Why is it called a Ternary expression, what does the word "Ternary" indicate?
- What is "use strict";? what are the advantages and disadvantages to using it?
- Create a for loop that iterates up to 100 while outputting "fizz" at multiples of 3, "buzz" at multiples of 5 and "fizzbuzz" at multiples of 3 and 5
```js
for (var i=1; i <= 100; i++){
  if(i%5==0 && i%3==0){
    console.log("FizzBuzz");
  }else if(i%5==0){
    console.log("buzz");
  }else if(i%3==0){
    console.log("fizz");
  }else{
    console.log(i);
  }
}
```
- Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?
Several reasons. 1) harder to read code 2)anyone can update a global variable from any point in the program at any time (and from any thread if there’s more than one going) 3)code smell/cutting corners 4)can encounter global variable name clashes
- Why would you use something like the load event? Does this event have disadvantages? Do you know any alternatives, and why would you use those?
- Explain what a single page app is and how to make one SEO-friendly.
A single page app is a website that loads the main container and then yields views based on user clicks. An example of a framework of this is Angular, where you can have different views populate the browser without refreshing the page. Tips for SEO: Paginate content, organize CSS for spiders, seek authority, multiple H1 tags, readability, "keep it fresh"
- What is the extent of your experience with Promises and/or their polyfills?
- What are the pros and cons of using Promises instead of callbacks?
- What are some of the advantages/disadvantages of writing JavaScript code in a language that compiles to JavaScript?
- What tools and techniques do you use debugging JavaScript code?
- What language constructions do you use for iterating over object properties and array items?
- Explain the difference between mutable and immutable objects.
  - What is an example of an immutable object in JavaScript?
  - What are the pros and cons of immutability?
  - How can you achieve immutability in your own code?
- Explain the difference between synchronous and asynchronous functions.
- What is event loop?
  - What is the difference between call stack and task queue?
- Explain the differences on the usage of foo between function foo() {} and var foo = function() {}

##HTML
- What does a doctype do?

A DOCTYPE is a required preamble.
DOCTYPEs are required for legacy reasons. When omitted, browsers tend to use a different rendering mode that is incompatible with some specifications. Including the DOCTYPE in a document ensures that the browser makes a best-effort attempt at following the relevant specifications.

- What's the difference between full standards mode, almost standards mode and quirks mode?

In quirks mode, layout emulates nonstandard behavior in Navigator 4 and Internet Explorer 5. This is essential in order to support websites that were built before the widespread adoption of web standards. In full standards mode, the behavior is (hopefully) the behavior described by the HTML and CSS specifications. In almost standards mode, there are only a very small number of quirks implemented.

- What's the difference between HTML and XHTML?
XHTML is 'stricter', it mimics XML markup. The HTML I write very much follows XHTML guidelines!
- Are there any problems with serving pages as application/xhtml+xml?
- How do you serve a page with content in multiple languages?
- What kind of things must you be wary of when design or developing for multilingual sites?
- What are data- attributes good for?
It's good to prefix to custom attributes. For example, angular uses "ng-" in it's html. This would fail a validator, so prefixing it with "data-" would allow it to pass validation.
- Consider HTML5 as an open web platform. What are the building blocks of HTML5?
- Describe the difference between a cookie, sessionStorage and localStorage.
- Describe the difference between <script>, <script async> and <script defer>.
- Why is it generally a good idea to position CSS <link>s between <head></head> and JS <script>s just before </body>? Do you know any exceptions?
- What is progressive rendering?
- Have you used different HTML templating languages before?

##CSS
- What is the difference between classes and IDs in CSS?
Both are "hooks", i.e. selectors, but IDs are unique and should only be used once. Classes can be used on multiple elements. IDs also can be used in url anchoring (www.example.com/index#comments).
- What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?
CSS resets strip down all the html formatting, leaving you with the ability to customize everything. Normalizing doesn't "unstyle" everything, so it preserves styles in browsers. For small projects, Normalize is fine. If I'm building a large scale project, I'd use reset.
- Describe Floats and how they work.
Floats move an image or an element to a certain part of the page to allow other content to wrap around it (while still following the "flow" of the page). A float mimics print media in this way.
- Describe z-index and how stacking context is formed.
Z-index allows for vertical stacking of elements on top of other elements. These elements have to be positioned non-statically (static being the default positioning value). Higher z-index gets stacked "closer" to the viewer.
- Describe BFC(Block Formatting Context) and how it works.
- What are the various clearing techniques and which is appropriate for what context?
I prefer to use the overflow: auto method. You can also place an empty div of <div style="clear:both;"></div> after the last floated item to do so, but then you clutter the html.
- Explain CSS sprites, and how you would implement them on a page or site.
- What are your favourite image replacement techniques and which do you use when?
- How would you approach fixing browser-specific styling issues?
- How do you serve your pages for feature-constrained browsers?
  - What techniques/processes do you use?
- What are the different ways to visually hide content (and make it available only for screen readers)?
- Have you ever used a grid system, and if so, what do you prefer?
- Have you used or implemented media queries or mobile specific layouts/CSS?
- Are you familiar with styling SVG?
- How do you optimize your webpages for print?
- What are some of the "gotchas" for writing efficient CSS?
- What are the advantages/disadvantages of using CSS preprocessors?
  - Describe what you like and dislike about the CSS preprocessors you have used.
- How would you implement a web design comp that uses non-standard fonts?
- Explain how a browser determines what elements match a CSS selector.
- Describe pseudo-elements and discuss what they are used for.
- Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.
- What does * { box-sizing: border-box; } do? What are its advantages?
- List as many values for the display property that you can remember.
- What's the difference between inline and inline-block?
- What's the difference between a relative, fixed, absolute and statically positioned element?
- The 'C' in CSS stands for Cascading. How is priority determined in assigning styles (a few examples)? How can you use this system to your advantage?
- What existing CSS frameworks have you used locally, or in production? How would you change/improve them?
- Have you played around with the new CSS Flexbox or Grid specs?
- How is responsive design different from adaptive design?
- Have you ever worked with retina graphics? If so, when and what techniques did you use?
- Is there any reason you'd want to use translate() instead of absolute positioning, or vice-versa? And why?

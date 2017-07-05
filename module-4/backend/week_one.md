## Week One - Module 4 Recap

Fork this repository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week. 

Note: When you're done, submit a PR. 

1. What's the most useful thing you learned from completing the intermission week work?
how to work with basic javascript, console.log, sort, reduce

2. What are some tools to help debug JavaScript code?
debugger, pryjs 

3. What are some tools you need in order to unit test your JavaScript?
mocha and chai

4. What is the syntax for invoking a function?
function();

5. What's the difference between `==` and `===` in JavaScript?
== is strict equal and === is absolute equal

6. What's the difference between asynchronous and synchronous JavaScript? 
I think JS is always synchronous in that it executes one line of code at a time, but it becomes asynchronous if a function makes a database call or API call because the code will continue executing below it without waiting for a response from the database or API...

7. How do we set up a route when creating an API with Node and Express?
Set up an instance of Express in (for example) a server.js file, then write the route as follows to handle an HTTP request for a root page of a website: 

name_of_express_app.get('/', function(request, response) {
  response.send(whatever_we_want_to_return_to_the_user_here);
})

8. What do we use Knex for?
It functions as the interface between node and the database -- we use SQL queries to get the information we want.

9. What's `npm` and what do we use it for?
node package manager -- similar to gems in ruby. we use it to install things like express, mocha, and chai and other dependencies that appear in our package.json file.

#### Review  
10. What's the MVC design pattern? Describe each part of MVC?
model-view-controller
As an HTTP request comes in, it's routed to the controller which tells the model what to search for and return from the database and the model returns it to the controller to render in the view, which is what the end user sees.

11. What is AJAX? What are some benefits of using AJAX?
Asynchronous Javascript And XML; it's small/compact, makes interacting with the DOM easier than vanilla JS, and helps users accomplish various objectives without page reload.

12. What's a background worker? When would we want to use a background worker?
A background worker is code that runs some action (usually something that takes time, such as a complex database query or email operation) in the background so as not to hold up the end user. For example, if a user registers an account on our website and we generate an email confirmation, it would be bad practice to make the user wait while the email action completes (or they may think the application is hanging and leave the page), so we would make that action a background worker so the user can continue on her way while the email action runs and completes.

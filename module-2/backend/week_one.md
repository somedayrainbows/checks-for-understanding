## Week One - Module 2 Recap

Note: When you're done, submit a PR. 

1. List the five common HTTP verbs and what the purpose is of each verb.
  GET (read), POST (create), PUT (update/replace), DELETE (destroy/delete), PATCH (modify)
2. What is Sinatra?
  Like "baby rails" -- more lightweight version of rails
4. What is MVC?
  "Model-View-Controller" -- framework for how our program interact with databases, servers and the web
5. Why do we follow conventions when creating our actions/path names in our Sinatra routes?
  for consistency and so our program will work/be functional
6. What types of variables are accessible in our view templates without explicitly passing them?
  Instance variables mentioned in a route are available in in the ERB rendered from/in the same route 
7. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?
  
  ```ruby
  get '/horses' do
    @count = 1
    erb :index
  end
  ```
8. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?
   ```ruby
  get '/horses' do
     @name = "Mr. Ed"
    erb :index
  end
  ```
9. What's the purpose of ERB?
  ERB is embedded ruby: you can embed ruby in an HTML format in a .erb file and render it in web pages (or xml)
10. Why do I need a development AND test database?
  for speed and to prevent any 
11. What's responsive design?
  designing for all environments (i.e. ensuring a site is functional and has a good UI on mobile AS WELL AS desktop, ipad, etc.)
12. What is CRUD and why is it important?
  it stands for Create Read Update and Delete - CRUD operations are important because it's a framework for how we use an MVC model to interact with data in an associated database
13. What does HTTP stand for?
  HyperText Transfer Protocol
14. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?
  <%= %>  --> displays whatever is inside the code on the rendered page
  <% %> --> runs the code inside the little code (sniplets? scripts?) but doesn't display/render anything on the rendered page
15. What's an ORM?
  Object Relational Mapping system/framework
16. What's the most commonly used ORM in ruby (Sinatra & Rails)?
  ActiveRecord
17. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.
  get "/menu"  --> (read) displays the list of all menu items
  get "/menu/new"  --> (read) displays a form that would allow a user to add a new menu item
  post "/menu"  --> (create) adds a row to the database with the form input from the previous page and displays the new info in the list of all menu items
  get "/menu/:id/edit"  --> (read) shows a form that will allow a user to edit an existing menu item
  put "/menu/:id"  --> (update/replace) replaces the existing data in the database for this id's record with the new info just entered by the user in the form and 
  get "/menu/:id"  --> (read) renders the newly updated data for this menu item on the id's page
  delete "/menu/:id"  --> (delete/destroy) deletes this id's record from the database 
18. What's a migration? 
  a method used to determine the structure of your database (defined in the schema file)
19. When you create a migration, does it automatically modify your database?
  if by "modify" you mean does it add data? no, it just sets up the structure of the database (column names etc.)
20. How does a model relate to a database?
  it is essentially the air traffic controller, it takes the commands from the controller and interacts with the DB in order to pull and send data to the Views docs to render it to an end user
21. What's the difference between agile workflow and waterfall method?
  agile is continuous rapid development whereas waterfall refers to traditional development that has discrete phases (and isn't as nimble as agile)
22. What is the difference between `#new` and `#create`?
  new doesn't save anything in the DB, create does.

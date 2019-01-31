# Server Comps

## MVC

Model view controller has been the default way to create web applications for a long time

1. The client makes a request
2. The server moves it to the correct route
3. The route sends it to the correct controller
4. The controller can do anything from reading data to writing data to something totally unrelated and then returns a view
5. Views are pages that you have created before hand and are stored on the server
6. Dynamic content can be rendered inside these pages with EJS, Handlebars, Pug, etc

### Pros
* Central development
### Cons
* Complexity of application
* Programmers need a wider amount of knowledge

## Rest API

While the MVC has one server working on all the work, Rest APIs have at least two servers. There is a server that is your front end and the server that is your API.

1. The client makes a request
2. The server sends back the appropriate information
3. The webpage that you have now makes requests through JS to your API server
4. The API server moves it to the correct route
5. The route sends it to the correct controller
6. The controller does what work that it needs to do and returns JSON information
7. The client now has the JSON information and parses it and does what it needs to

### Pros
* Parallel team development
* Faster development cycle
* Separation of concerns - business logic and presentation are seperate
* Allow focus on individual peices and the ability to change one without interfering with the other
* Pages dont have to releod all the time and instead routing is handled within the client side
* Stateless - each request is treated as its very own request with no information needing to be stored from the previous request
* Uniform responses

### Cons
* Large amounts of data sometimes - data that you dont need - Overfetching (extra network usage that you dont need plus client parsing)
* May cause waterfall calls for data (e.g. call the title of a book, then the author, then the first chapter, etc)
* Many different connection areas and routes returning different things
* Trying to redo routes can be difficult and time consuming and resource intense on the team when you need to change the architecture

## GraphQL

GraphQL feels like a type of Rest API even though it isnt. It is a Query Language which is to say that it is a way to ask the server for something very specific and get hat thing back. Most likely you will have the same set up as a Rest API (see the numbered list above under Rest API section.

The main thing to know about GraphQL is that it helps with the cons we mentioned about Rest APIs. When querying a Rest API, you may get so much more information than you need. Perhaps you only need the title of all posts but the API is set up to return body, user, time, etc. All of that is useless information to you if you only need the title. GraphQL allows you to query only for the specific information that you need

### Pros
* Use one route for all requests
* Get back only the information that you need

### Cons
* Rate limiting - a graphQL query may be very resource intensive or not at all depending what you need back. It can be hard to know who is using complex queries and limiting them vs a nonintexive query

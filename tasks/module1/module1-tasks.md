# Configuring Websockets on the server

## Install the ws npm dependency
TASK 1:
In the terminal at the root of the project, run the command `npm install ws`. 
Running that command will add an entry for `ws` in the `package.json` file 
and install the `ws` library in `node_modules`.

## Require the ws library
TASK 2:
In `bin/www` require the built-in Node library `ws` and store a reference to it 
in a `const` called `WebSocket`.

## Create a Websocket using the existing Express server configuration
Task 3: 
In `bin/www` create a `const` called `wss` and assign it to a new 
`WebSocket.Server` instance. The `WebSocket.Server` constructor requires a
`WebSocket.ServerOptions` object. Use the existing Express `server` variable
for the `WebSocket.ServerOptions` object's `server` property.





# Adding the Websocket-based log viewer window

## Add a log viewer panel
TASK 1:
In the `views/index.ejs`  file complete the following:
* Inside the existing `div` with class `container` below the title header, add another `div` 
  element with classes of `panel` and `panel-default`.
* Inside the `div` created above, add another `div` with a class of `panel-heading`. 
  For the `div` content add the text `"Log Viewer"`.
* Inside the `div` with classes `panel` and `panel-default` and below the div.

## Create the log viewer javascript file
TASK 2:
At the root of the project create a directory called `public`. Inside that directory 
create a directory called `javascripts`.
Inside the `public/javascripts` directory create a file called `log-viewer.js`





## Set the form's encoding and action
TASK 2:
Let's add some attributes to our `form` tag. Add a `method` of `'post'` to the 
`form`. Add an `enctype` attribute with the string `'multipart/form-data'` to 
the `form` tag. Add an `action` attribute with the string `'/upload'`. Note: In this
project all HTML attribute values must have no spaces in them. 

## Add an input
TASK 3:
Inside our `form`, add an `input` with a `class` name of `'file-input'`. Give it a `type` attribute with the string value `'file'`.
Then, give it a `name` attribute with the string value of `'photo'`.

## Add a submit button
TASK 4:
Next we will add a submit button. Under our file `input`, let's create another `input` tag.
It should have a `class` of `'submit-button'`, a `type` attribute of `'submit'`, and a `value` attribute of `'Submit'`.

## Export the app
TASK 5:
For our next task, we will need to create our server. Let's open up `app.js`, which is inside the `api` directory. Let's start out by requiring `'express'` 
and `'path'`. Next, create a `const` called `app`, and let's assign a call to 
the `express()` function. Next, let's `export` our `app` on the `module.exports` 
object.

## Respond with the form
Task 6:
Right above our `module.exports` line, let's define a constant `pathToIndex` to represent the path to our `index.html` file. Call `path.resolve()`, and assign it to the constant we just created. Let's pass `__dirname` as the first argument, and a string value of `'../client/index.html'` as the second argument. 


Let's call the `use()` method of our `app`. 
For the _route_ argument, let's pass a string of `'/*'`. For the route handler, 
we will pass an anonymous function that takes two parameters, `request` and 
`response` in that order. Our route handler should call the `sendFile()` method 
of our `response` parameter. As its first argument, use the path to the index file `pathToIndex` we previously defined.

Module Outro:
At this point we have a working server that will serve our upload page.
Let's run `npm run start` to start up our server. Let's open up our browser and go to localhost port 3000.
# Homework: Full Stack Games Hub App

### Learning Objectives

- Understand the relationship between client, server and database
- Be able to navigate a codebase that you haven't written

## Brief

Your boss has asked to you look over the codebase of a full-stack JavaScript application. The front-end is written in JavaScript using React, the back-end uses an Express server and a MongoDB database. Your task is to make yourself familiar with the codebase.

The application includes a README.md with instructions on running the application.

![Overview of the tech stack and tooling with commands](images/tech_stack_with_commands.png)

*Overview of the tech stack and tooling with commands*

*EDIT: Frontend is now written in React with the command to run `npm start`*

## MVP

### Task

Draw a diagram showing the dataflow through the application starting with a form submission, ending with the re-rendering of the page. This will involve a multi-direction data-flow with the client posting data to the server and the server sending data back to the client with the response. Detail the client, server and database in the diagram and include the names of the files involved in the process.

### Questions

1. What is responsible for defining the routes of the `games` resource?
   
    gamesRouter

2. What do you notice about the folder structure?  Whats the client responsible for? Whats the server responsible for?
   
    The server is responsible for the backend. The client is responsible for the frontend.

3. What are the the responsibilities of server.js?
    
    - listening for requests
    - connecting to games_hub database
    - passing games collection to router
    - routing for games

4. What are the responsibilities of the `gamesRouter`?
    
    gamesRouter defines the routes for games

5. What process does the the client (front-end) use to communicate with the server?

    Fetch requests through GamesService to server

6. What optional second argument does the `fetch` method take? And what is it used for in this application? Hint: See [Using Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch) on the MDN docs

    Init object used to specify request, see POST and DELETE (GamesService.js)

7. Which of the games API routes does the front-end application consume (i.e. make requests to)?

    GET, POST, DELETE

8. What are we using the [MongoDB Driver](http://mongodb.github.io/node-mongodb-native/) for?

    We use it to interact with database from the js application

## Extension

Why do we need to use [`ObjectId`](https://mongodb.github.io/node-mongodb-native/api-bson-generated/objectid.html) from the MongoDB driver?

    We can't query a database for object of a specific ID using a string, it won't find a match. We need to first create an ObjectID.

Add to your diagram the dataflow for removing a game.

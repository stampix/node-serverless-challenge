# Stampix Node.js & Serverless challenge

## Setting
Cloud-based AWS Lambda functions with a Node.js 12 runtime written in TypeScript.

## Goal
This repository contains a populated SQLite database consisting of 50 users. The goal is to create 3 functions, corresponding to 4 operations on the database: creation, retrieving, listing & searching.

The following REST API is set up already for you (see Practical):

1. A list of users: `GET http://localhost:3000/users`
2. Get a specific user: `GET http://localhost:3000/user/{id}`
3. Create a user: `POST http://localhost:3000/user`

Endpoint one should both be able to:

1. List all users
2. Find all users with a specific first name

Endpoint two and three are straight-forward.

## Practical
1. Clone this repo and install the already existing development dependencies.
2. Install [AWS SAM](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-install.html)
3. Write your functions according to AWS Lambda standards using the Node.js 12 runtime inside `/src/*.ts`
4. Start the compiler using `yarn watch`, this will pro-actively compile your changes .
5. In another terminal, run a local server using `yarn start`, this will make the local endpoints available.

Note: SAM CLI is not the most optimal

### Notes:
The SAM CLI runs your code inside docker containers simulating the Lambda environment. If you're developing on non-compatible platform, you might get an error like this:

`Runtime.ImportModuleError: Cannot find module '/var/task/node_modules/sqlite3/lib/binding/napi-v3...`

You might have to manually additionally install the appropriate SQLite binaries:

`cd node_modules/sqlite3 && npm run install -- --target_platform=linux --target_arch=x64 && cd ../..`



## Requirements
1. The 3 functions should do what they are supposed to do according to the goals of this challenge.
2. You should add automatic testing and make sure that `yarn test` does what could be expected of it in a CI/CD context.
3. Document your code as you would in any collaborative project

## Food for thought
Think about the following questions and formulate an answer below. Think about the difficulties or edge-cases you would encounter. How would you tackle these?

The number of users suddenly increases to over 10,000. What comes to your mind with relationship to the functionality you just wrote?

Have a look at the datastructure of the database (i.e. have a look at `scripts/populate.js`). Now assume that we are not using SQLite, but MySQL 8. What would you do differently?

Suppose we want to set up a search function for the users where we can search with an arbitrary input value. How would you do this?

### Your answers

<!--
Write down your answers here
-->

## Delivery
- Anything that is not enforced in the base repository (tools, dependencies, architecture, frameworks, ...) is free of choice
- Push your solution to your Git platform of choice, as long as it's public.

**Note**: There's no need to actually use the AWS Cloud.

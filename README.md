# devops-todos

A minimal project for learning about end-to-end testing.

## Installation

To install dependencies, run the following command in `server` and in `client`:

```bash
npm install
```

Make sure you have MySQL installed and running on your computer, with a database called `testing_todos`.

## Running

To run the server, use:

```bash
npm run start:dev
```

To run the client, use:

```bash
npm run dev
```

<!-- TODO: -->

## Step 1:

Create a dockerfile for the server
It should copy the packages, install dependencies, copy the relevant code, build the img and run the server.
THe image

you'll know you've got it right when running:
docker run <your img>
returns an error of "unable to connect to the database".
Later in the deployment,

## Step 2:

Create a dockerfile for the client
It should copy relevant packages, install dependencies, copy the relevant code, build the img and run the server.

you'll know you've got it right when running:
docker run <your img>
returns an text ending in "app started successfully".

## Step 3:

Party-Party\*

\*in your own preferred way\*\*
**as long as it's legal\***
\*\*\*and doesn't harm anyone

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

Create a dockerfile for the server:
It should copy the packages, install dependencies, copy the relevant code, build the img and run the server.

build the docker image:
docker build -f client/Dockerfile -t <name your img> .

run the docker image:
docker run <your img>

you'll know you've got it right when running the docker image returns an error of "unable to connect to the database".
Later in the deployment, the database is connected. :)

## Step 2:

Create a dockerfile for the client
It should copy relevant packages, install dependencies, copy the relevant code, build the img and run the client.

you'll know you've got it right when running:
docker run <your img>
returns a text that includes "ready for start up".
It ends with a "host not found" error because it can't find the server. That connection is done later in the deployment.

## Step 3:

Party-Party\*

\*in your own preferred way\*\*
**as long as it's legal\***
\*\*\*and doesn't harm anyone

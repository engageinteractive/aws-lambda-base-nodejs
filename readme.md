# [Project devs to add: Project name]

## Project background
[Project devs to add: Add a short description about what this project codebase is.]

## Project architecture
[Project devs to add: Add a short description on codebase architecture.]

This project runs in AWS Lambda, using the Node 10 runtime.

## Running a local version
The Lambda function can be ran locally via a Docker container.

To run your function, run `scripts/console`

### Prerequisites
1) [Download](https://docs.docker.com/docker-for-mac/install/) and install Docker Desktop for Mac.
2) Ensure no other applications are using the same ports as the Docker containers in this projects use.

### Establish a running environment

##### 1. Starting up service containers:
To start the project, run `scripts/bootstrap`.
If this is the first time checking out the project. The script will create an environment file from the example file, and run any application initialistion scripts.

### Scripts reference
##### `scripts/bootstrap`
Use the bootstrap script to start a project in an initialised state.
**Usage:**: `$ scripts/bootstrap [args]`

| Argument        | Description   |
| --------------- |---------------|
| **--no-update** | Makes the script skip application dependency installation |

This script creates a .env file if one isn’t present, builds and starts the Docker service containers, installs applications dependencies (Composer packages, Node modules, Database schema, and seeding data), and generates an application key.

##### `scripts/update`
**Usage:**: `$ scripts/update`
Update installs application dependencies inside app container. For example Composer packages, Node modules, Database schema, and seeding data

##### `scripts/build`
**Usage:** `$ scripts/build [command]`
Build is used for building/compiling javascript, and running Yarn. If no command is passed, the script will run yarn’s development build task.

##### `scripts/test`
**Usage:** `$ scripts/test`
Test runs the applications testing suite.

##### `scripts/console`
**Usage:** `$ scripts/console [args]`
Console runs the local aws lambda. If no command is passed, it will run the handler method in `src/index.js`

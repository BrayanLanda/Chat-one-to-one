# Chat Application

This is a real-time chat application built using **Spring Boot**, **MongoDB**, **WebSockets**, and **Docker**. The application supports real-time messaging between users and stores the chat history in a MongoDB database.

## Table of Contents

- [Features](#features)
- [Technologies](#technologies)
- [Requirements](#requirements)
- [Installation](#installation)
- [Running the Project](#running-the-project)
    - [Running with Docker](#running-with-docker)
    - [Running Locally](#running-locally)
- [API Endpoints](#api-endpoints)
- [License](#license)

## Features

- Real-time messaging using WebSockets.
- Persistent message storage with MongoDB.
- Dockerized environment for easy deployment.
- Mongo Express to visualize MongoDB collections.

## Technologies

- **Backend**: Spring Boot (Java)
- **Database**: MongoDB
- **WebSockets**: STOMP over WebSocket
- **Frontend**: To be developed (HTML, CSS and JavaScript.)
- **Docker**: Docker Compose to manage MongoDB and Mongo Express

## Requirements

To run this project, you will need:

- Java 17+
- Spring Boot
- Docker & Docker Compose
- MongoDB
- Mongo Express (for visualization)

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/BrayanLanda/Chat-one-to-one.git
    cd Chat-one-to-one
    ```

2. Set up the environment variables for MongoDB in `application.yml` or `application.properties`:
    ```yaml
    spring:
      data:
        mongodb:
          host: localhost
          port: 27017
          database: chat_app
    ```

3. If you want to change the MongoDB connection or credentials, modify the configuration under `src/main/resources/application.yml`.

## Running the Project

### Running with Docker

1. Make sure Docker and Docker Compose are installed.

2. Build and run the containers:
    ```bash
    docker-compose up --build
    ```

3. MongoDB and Mongo Express will run in containers. Mongo Express will be available at `http://localhost:8081`, and the Spring Boot application will run on `http://localhost:8088`.

### Running Locally

1. Make sure MongoDB is installed and running locally on port `27017`:
    ```bash
    sudo systemctl start mongod
    ```

2. Run the Spring Boot application:
    ```bash
    ./mvnw spring-boot:run
    ```

3. The application will be running on `http://localhost:8088`.

## API Endpoints

- **WebSocket Endpoint**: `/ws`
    - The WebSocket connection for real-time messaging.

- **Rest Endpoints** (for possible future use):
    - `POST /messages`: Send a message (via HTTP API).
    - `GET /messages`: Get all messages.
    - `GET /users`: Get a list of users.

## License

The license for this project has not been determined yet.
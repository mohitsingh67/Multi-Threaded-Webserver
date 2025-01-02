
# Multithreaded Web Server

This project demonstrates a simple multithreaded web server and client application implemented in Java. The server listens for incoming connections from clients and responds with a greeting message. Each client request is handled in a separate thread, ensuring that the server can process multiple client requests concurrently.

---

## Features

- **Multithreaded Server:** Handles multiple clients simultaneously by creating a new thread for each connection.
- **Client-Server Communication:** Clients connect to the server, send a greeting, and receive a response.
- **Socket Programming:** Utilizes Java socket programming to establish communication between the client and the server.

---

## Prerequisites

Ensure you have the following installed on your system:

- **Java Development Kit (JDK):** Version 8 or higher
- **IDE or Text Editor:** Any Java-compatible editor (e.g., IntelliJ IDEA, Eclipse, or VS Code)
- **Terminal/Command Prompt**

---

## How to Run the Project

### Step 1: Compile the Code

1. Open a terminal or command prompt.
2. Navigate to the directory containing the project files (`Client.java` and `Server.java`).
3. Compile the server and client code:
   ```bash
   javac Server.java Client.java
   ```

### Step 2: Start the Server

1. Run the server program to start listening for connections:
   ```bash
   java Server
   ```
2. The server will start listening on port `8010` and display the following message:
   ```
   Server is listening on port 8010
   ```

### Step 3: Start the Client(s)

1. Open a new terminal or command prompt.
2. Run the client program to simulate multiple clients connecting to the server:
   ```bash
   java Client
   ```
3. The client program will create 100 threads, each connecting to the server and sending a greeting message.

### Step 4: Observe the Communication

- The server will respond to each client with a message like:
  ```
  Hello from server /127.0.0.1
  ```
- Each client will display the server's response in the console:
  ```
  Response from Server Hello from server /127.0.0.1
  ```

---

## Project Structure

```
.
├── Client.java    # Client-side implementation
├── Server.java    # Server-side implementation
└── README.md      # Documentation (this file)
```

---

## Code Overview

### Server
- Listens on port `8010`.
- Uses a `ServerSocket` to accept client connections.
- Spawns a new thread for each client to handle requests concurrently.
- Sends a greeting message to the client.

### Client
- Connects to the server on `localhost` and port `8010`.
- Sends a greeting message to the server.
- Reads and displays the server's response.
- Creates 100 threads to simulate multiple clients connecting simultaneously.

---

## Notes

- Ensure that the server is running before starting the client program.
- The server's `setSoTimeout` is set to 10 seconds. If no client connects within this duration, the server will stop listening for connections.
- Modify the port number if `8010` is already in use on your machine.

---

## Improvements and Extensions

You can extend this project by adding the following features:

1. **Dynamic Client Requests:** Allow clients to send different types of requests and process them on the server.
2. **Logging:** Add logging to track client connections and messages.
3. **Load Balancing:** Distribute client connections across multiple servers.
4. **Error Handling:** Implement more robust error handling for client and server interactions.

---

Enjoy exploring socket programming with this multithreaded web server! 🚀

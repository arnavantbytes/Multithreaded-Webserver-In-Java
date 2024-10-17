Here's a README file for your multithreaded server-client application based on the code you shared:

---

# Multithreaded Server-Client Application

This repository contains a simple multithreaded server-client application built using Java. The server handles multiple concurrent client connections, with each client sending a message to the server and receiving a response. Both server and client are implemented using sockets and multithreading techniques.

## Features

- **Multithreaded Server**: The server handles multiple clients concurrently by spawning a new thread for each client connection.
- **Multithreaded Clients**: The client spawns multiple threads, with each one connecting to the server simultaneously.
- **Socket Communication**: Clients and server communicate using TCP/IP sockets.
- **Java Functional Programming**: The server leverages the `Consumer` functional interface for clean and modular handling of client connections.

## Technologies Used

- **Java Sockets**: Used for communication between server and client.
- **Multithreading**: Java `Thread` is used to manage concurrent execution on both the server and client side.
- **Functional Interface**: The server uses Java’s `Consumer<Socket>` to handle client connections in a functional style.

## Code Structure

### Client

- The `Client.java` creates multiple threads, each of which opens a socket connection to the server and sends a simple message.
- The client waits for the server's response and prints it to the console.

### Server

- The `Server.java` listens on a specified port for incoming client connections.
- For each incoming connection, the server creates a new thread, assigns it the task of handling that client’s request, and sends a response back.

## How to Run

### Prerequisites

- **Java JDK**: Make sure you have JDK 8 or higher installed.

### Steps

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/arnavantbytes/Multithreaded-Webserver-In-Java.git
   cd multithreaded-server-client
   ```

2. **Compile the Code**:
   Compile both the server and client:
   ```bash
   javac Server.java Client.java
   ```

3. **Run the Server**:
   In a terminal, run the server:
   ```bash
   java Server
   ```
   This will start the server, listening on port `8010` for incoming connections.

4. **Run the Clients**:
   Open another terminal, and run the clients:
   ```bash
   java Client
   ```
   This will start 100 concurrent client threads, each sending a message to the server and receiving a response.

### Expected Output

- **Server Output**:
  ```
  Server is listening on port 8010
  Response sent to client /127.0.0.1
  Response sent to client /127.0.0.1
  ```

- **Client Output**:
  ```
  Hello from Client /127.0.0.1
  Response from Server: Hello from server /127.0.0.1
  ```

## Troubleshooting

- **Connection Refused**: If you encounter a `java.net.ConnectException: Connection refused`, ensure that the server is running and is able to accept connections on the specified port.
- **System Performance**: Running 100 concurrent clients might consume significant system resources. If your machine struggles, consider reducing the number of clients or adjusting thread pool sizes.

## License

This project is licensed under the MIT License.

---

You can adjust the URLs, project names, or other specifics based on your project needs before uploading it to GitHub.

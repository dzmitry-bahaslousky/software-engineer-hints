The **WebSocket API** is a protocol that allows for full-duplex communication (i.e., two-way communication) between a client (typically a web browser) and a server over a single, long-lived connection. Unlike traditional HTTP communication, which is request-response-based, WebSockets allow both the client and server to send messages to each other independently, without the need for the client to request data repeatedly.

### Key Features of WebSocket API:

1. **Full-Duplex Communication**: Both client and server can send data at any time, simultaneously, over the same connection. This is particularly useful for real-time applications.
    
2. **Persistent Connection**: Once a WebSocket connection is established, it stays open until explicitly closed, unlike HTTP, where a new connection is opened for each request and closed immediately after the response.
    
3. **Low Latency**: WebSockets reduce overhead because after the initial handshake, data is sent over a single connection without the need for repeated HTTP requests, making it ideal for applications that require real-time updates, such as chats, gaming, and stock price updates.
    
4. **Message-Based Communication**: Instead of exchanging request/response headers, the client and server communicate using lightweight frames. Messages are passed in either **text** or **binary** format.
    

### How the WebSocket API Works:

1. **Handshake**: A WebSocket connection starts with an HTTP-based handshake initiated by the client. The client sends an HTTP request to the server to upgrade the connection to WebSocket.

**Client Request**:
```makefile
GET /chat HTTP/1.1
Host: example.com
Upgrade: websocket
Connection: Upgrade
Sec-WebSocket-Key: dGhlIHNhbXBsZSBub25jZQ==
Sec-WebSocket-Version: 13
```

**Server Response**:
```makefile
HTTP/1.1 101 Switching Protocols
Upgrade: websocket
Connection: Upgrade
Sec-WebSocket-Accept: s3pPLMBiTxaQ9kYGzzhZRbK+xOo=
```

2. - **Communication**: After the handshake, the connection is upgraded to a WebSocket connection, and both the client and server can send messages to each other.
    - Messages are exchanged as frames. Each frame can contain a small piece of data (e.g., a text message, binary data, or control frames for closing the connection).

3. **Closing the Connection**: Either side can close the connection at any time by sending a "close" frame, and the other side acknowledges this with a "close" frame as well.

### Example of WebSocket API in JavaScript

A simple WebSocket connection can be established in JavaScript using the `WebSocket` object:

```javascript
// Create a new WebSocket connection
const socket = new WebSocket('ws://example.com/socket');

// Event listener when connection is open
socket.onopen = function(event) {
  console.log("Connection opened!");
  // Send a message to the server
  socket.send("Hello Server!");
};

// Event listener for receiving messages
socket.onmessage = function(event) {
  console.log("Message from server: " + event.data);
};

// Event listener for closing the connection
socket.onclose = function(event) {
  console.log("Connection closed!");
};

// Event listener for error
socket.onerror = function(error) {
  console.error("WebSocket error:", error);
};
```

### Use Cases of WebSockets:

- **Real-Time Applications**: WebSockets are perfect for applications that require real-time communication such as chat applications, multiplayer games, live sports updates, stock trading platforms, etc.

- **Live Data Streaming**: Used for real-time data streaming like live video or audio streams.

- **Collaborative Tools**: Applications like collaborative document editing (e.g., Google Docs) or drawing boards can use WebSockets to synchronize changes between multiple users in real time.


### Differences Between WebSockets and HTTP:

- **Communication Model**: HTTP is request/response-based (client requests, server responds). WebSockets are bidirectional.
- **Connection Persistence**: HTTP typically closes the connection after each request, whereas WebSockets keep the connection open for continuous communication.
- **Overhead**: WebSockets have less communication overhead than HTTP because there’s no need for repeated headers after the initial handshake.

### Conclusion:

The **WebSocket API** is a powerful tool for creating real-time, interactive applications on the web. By maintaining an open, bidirectional communication channel, WebSockets allow servers to push data to clients without waiting for client requests, significantly improving the responsiveness and performance of applications like online games, chat apps, and live dashboards.
Lab 04: Simple Token Authentication with Flask

Overview
This project is a basic example of how a server and a client can talk to each other using tokens for secure access. The server is built with Flask, and the client is a Python script. The client logs in to get a token, then uses that token to send a message, which the server echoes back if the token is correct.

Files
- my-server.py: The server code. It handles logging in, creating tokens, and checking tokens when the client sends messages.
- my-calls.py: The client code. It logs in to get a token and then uses the token to send a message to the server.

How It Works
1. Server (my-server.py)
   - /login: The client sends its ID (like an email) to this route, and the server sends back a token.
   - /echo: The client sends a message with the token here. If the token is valid, the server repeats the message back.

2. Client (my-calls.py)
   - Logs in by sending an ID to the /login route and gets a token in return.
   - Uses that token to send a message to /echo. If the token checks out, the server echoes the message.

Running the Project

1. Start the Server
In your Codespace terminal, run:
python3 my-server.py

2. Run the Client
On your MacBook (or wherever you’re running the client), go to the folder with my-calls.py and run:
python3 my-calls.py

Expected Output
- Successful Login and Message:
    Token received: f99aa8b8573062e9802f4fc0807ae1cb
    200
    You said: Hello Rainer!

- Failed Message (Invalid Token):
    403
    Invalid token

Requirements
- Python 3
- Flask (for the server)
- httpx (for the client)

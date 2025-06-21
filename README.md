# Tech Stack
Frontend: React, Socket.IO Client

Backend: Node.js, Express, Socket.IO Server

Other: React Scroll-to-Bottom, CORS

# Features
Join chat rooms with a username

Send and receive messages in real time

Scrolls to the newest message automatically

UI distinction between your messages and others'

Lightweight and responsive interface

# Project Structure
pgsql
Copy
Edit
/client
  └── App.js
  └── Chat.js
  └── index.js
/server
  └── index.js
# Getting Started
1. Clone the Repository
bash
Copy
Edit
git clone https://github.com/your-username/realtime-chat-app.git
cd realtime-chat-app
2. Start the Backend Server
bash
Copy
Edit
cd server
npm install
node index.js
The backend will run on: http://localhost:3001

3. Start the Frontend React App
bash
Copy
Edit
cd client
npm install
npm start
The frontend will run on: http://localhost:3000

# Usage
Enter your username and the room name.

Click “Join Room”.

Start chatting with others in that room.

# Core Logic Summary
Frontend: Chat.js
Sends messages with author, room, message, and timestamp via socket.emit("send_message", data)

Listens for "receive_message" and appends it to messageList

Scrolls to the bottom using react-scroll-to-bottom

Sends message on Enter key press or Send button click

Backend: index.js
Accepts client connections via Socket.IO

Handles: 

join_room: Adds user to specific room

send_message: Broadcasts message to room using socket.to(room).emit(...)

disconnect: Logs disconnection
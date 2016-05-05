![alt text](https://f.cloud.github.com/assets/220864/730169/feb98294-e24b-11e2-903d-b3cbc68f3a48.gif "Action Video")

## An intuitive collaborative drawing web based tool.
Collaborative real-time drawing, sketching & painting

Fast, light weight, easy to maintain.  Try the [demo] (http://draw.etherpad.org).

Demo
----
[Etherdraw Demo site](http://http://69.204.137.215:9002)

Installation
------------
  1. Install Requirements. ``sudo apt-get update && sudo apt-get install libcairo2-dev libjpeg8-dev libpango1.0-dev libgif-dev build-essential g++``
  2. Install EtherDraw `` git clone git://github.com/JohnMcLear/draw.git ``
  3. Enter the EtherDraw folder `` cd draw ``
  4. Run EtherDraw `` bin/run.sh `` 
  5. Make a drawing!  Open your browser and visit `` http://127.0.0.1:9002 ``
  
Note
----
If there is an error with node packages or npm package manager, install the correct versions:
  1. `` sudo npm install -g n ``
  2. `` sudo n 0.10.25 ``
  3. `` sudo npm install -g npm@1.3.10 ``

Requirements
------------
 * [NodeJS] (http://nodejs.org/)
 * Lib Cairo
 * Lib Jpeg
 * Lib Gif

Control Flow
------------
bin/run.sh - Shell Script to start Server
draw/server.js - Server Code, interacts with Client
draw/src/static/js/draw.js - Client Code, interacts with Server
draw/src/util/draw.js - Server Utility, interacts with Database

  1. Client connects to Server via :9002
  2. Client draws path locally
  3. Client emits draw:progress or draw:end event with path information in JSON
  4. Server receives draw:* event and JSON
  5. Server emits draw:* event with JSON to all Clients
  6. Server draws the path locally and stores in db (so new connections to the room can see drawing)

License
-------
Apache 2 License

Donations
---------
Donate to the [Etherpad Foundation] (http://etherpad.org/#links)

A detailed tutorial on building a basic web server with Node.js and the Express framework is given in this document. Upon accessing the webpage, users will receive an HTML file from the server. This tutorial is designed for novices who wish to learn how to serve static files using Express.
Prerequisites
Make sure the following software is installed on your computer before continuing: 
• Node.js: Get it from the official website and install it. 
• Node.js comes with NPM (Node Package Manager). 

1. Start a new Node.js project.
 
1. Launch a command prompt or terminal. 

2. Make a new project directory, then enter it: 

Command 

mkdir Task2.1 
cd Task2.1 

3. Launch a fresh Node.js project by executing:
 
npm init -y 

This program generates a package.json file that controls your project's dependencies and configurations. 

Step 2: Install Express
Express is a well-liked framework for Node.js web application development.
To install it, run: 

npm install express 

This will update package.json with the Express dependency and create a node_modules folder. 

Step 3: Create a Public Directory and an HTML File
1. Make a public folder inside the project directory: 
             mkdir public


2. Make an index.html file inside the public folder: 

touch public/index.html

When users access the web server, they will see the page.

Step 4: Create the Express Server
1. In the root directory, create a new file called server.js: 
touch server.js
2.Launch a text editor and enter the following code into server.js: 

       const express = require('express');
const path = require('path');
const app = express();
const PORT = 3001;
// Serve static files from the 'public' directory
app.use(express.static(path.join(__dirname, 'public')));
// Define a route for the home page
app.get('/', (req, res) => {
    res.sendFile(path.join(__dirname, 'public', 'index.html'));
});
// Start the server
app.listen(PORT, () => {
    console.log(`Server is running at http://localhost:${PORT}`);
});
                
3. The following is what this script does: 

                       * 	Brings in the path module and Express. 
                       *	A new Express application is started. 
                       * 	To provide static files, a public directory is defined. 
                       * 	The index.html file is served by defining a route (/). 
                       * 	 Logs a message in the console and launches the server on port 3000. 

Step 5: Run the Web Server
1. Launch the server by executing node server.js. 

2. The following message ought to appear in the terminal if the server starts successfully: 
The server can be found at http://localhost:3001. 

3. To view your webpage, type http://localhost:3001/ into a web browser. 

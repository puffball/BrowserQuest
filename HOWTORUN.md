Short instruction on how to build and run _BrowserQuest_ locally.  

Make sure you have a current version of nodejs and npm (https://nodejs.org).  
You also need a web server, for example _http-server_ which can be installed with npm:  

`$ npm install http-server -g`  

###### Download external dependencies
`$ cd BrowserQuest`  
`$ npm install # downloads and installs external libraries`  

###### Configure the client
`$ cd client/config`  
`$ cp config_local.json-dist config_build.json # copy config file`  

Edit config_build.json and set "host" to "127.0.0.1". The file should look like this:

    {
      "host": "127.0.0.1",
      "port": 8000,
      "dispatcher": false
    }

###### Build the client
`$ cd ../../bin`  
`$ chmod +x build.sh # make build.sh executable`  
`$ ./build.sh # builds the client in /client-build`  

###### Start the world server and web server hosting the client
`$ cd ..`  
`$ node server/js/main.js # starts the world server on port 8000`  
`$ cd client-build`  
`$ http-server . # starts a web server on port 8080`  

Go to http://localhost:8080 and you should see the _BrowserQuest_ start screen.

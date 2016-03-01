# BlindLunch

Source code for the BlindLunch app

# Prerequisites
1. Node & NPM. Get it.
2. Ionic CLI & Cordova ``` npm install -g ionic, cordova ```

# Setup
1. Fork this repo. This is merely the parent repo that contains the .gitmodules and references to client and server submodules
2. Clone your fork with ``` --recursive ``` flag and cd into it
3. add a remote upstream pointing to this parent ``` git remote add upstream [url] ```
4. Pull down the submodules ``` git submodule update --init --recursive ```
5. ``` cd ``` into the API and run ``` npm install ```
6. Run ``` node server ``` or if you have nodemon, simply run ``` nodemon ``` to start locally
7. cd into the client and run ``` npm install ``` and then ``` ionic serve ```

## Pulling
- ``` git fetch upstream --recurse-submodules  && git merge upstream/master && git submodule update --recursive ```
- ``` git submodule update --remote --merge ```

# Code Structure
There are two main submodules in Blind Lunch, the client and server

## Server 
The server is an express RESTful API with the following structure:
``` 
-/api //where all the routes go
    --/[endpoint]
      ---index.js //exports express mini app. uses controller to fetch data in and out of model
      ---controller.js
      ---model.js //will be used to enforce schema and any granular firebase interactions (this could change)
-/auth
    --/[oAuth platform]
      ---index.js //exports the authentication
      ---passport.js //passport config for each provider
-/config //server configuration. environmental variables, setup.
    --/envrionment
      ---index.js //responsible for detecting environment and merging properties and keys
      ---development.js
      ---production.js
    --express.js //sets up express server defaults based on environment
    --local.env.js
-app.js //wire express app all together and expose the app
-routes.js //all express mini apps are added as routes to main express app here. 
-index.js //export the configured app 

```

## Client
The client structure has not been determined, but will be most likely structured like a typical Ionic app
    

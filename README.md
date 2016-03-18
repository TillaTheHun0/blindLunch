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
The Server structure will need to revisited, once client side interactions with firebase is more concrete

## Client
The client structure will be a typical Ionic App structure and handle authentication with Firebase directly. 
    

Running Eclipse Luna inside a Docker container
---------------------------------------------

## Preliminary note

This image is based on these blog entries

* http://fabiorehm.com/blog/2014/09/11/running-gui-apps-with-docker/ 
* http://www.lorenzobettini.it/2012/10/installing-eclipse-features-via-the-command-line/

Thanks to the authors :)

## What's installed?

* Eclipse Lunar SR1 for RCP and RAP developers

### Plugins

 * Findbugs
 * Checkstyle
 * Database Viewer
 * Memory Analyzer
 * QuickREx
 
### Tools (command line, use e.g. in wicket shell)

 * gradle
 * ant
 * git
 * meld

## Download and run it 

    sudo docker run -it \
        -v ~/workspace/:/home/developer/workspace/ \
        -e DISPLAY \
        -v /tmp/.X11-unix:/tmp/.X11-unix \
        joemat/docker-eclipse-for-rcp


## Build the image from Dockerfile

    git clone https://github.com/joemat/docker-eclipse-for-rcp.git
    cd docker-eclpse-for-rcp
   
    # (optional: adjust UID, GUI and User in Dockerfile)

    sudo docker build -t eclipse-for-rcp .
   
    # run the image
    sudo docker run -it -v ~/workspace/:/home/developer/workspace/ \
        -e DISPLAY \
        -v /tmp/.X11-unix:/tmp/.X11-unix \
        eclipse-for-rcp

     

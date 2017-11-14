---
layout: page
title: Get MSGalaxy
description: >
  Here you will find information on obtaining and setting up a MSGalaxy instance with default configuration.
menu: true
order: 2
---

Here you will find information on obtaining and setting up a MSGalaxy instance with default configuration.
{:.message}


## Requirements
* UNIX/Linux or Mac OSX
* Python 2.7
{:.related-posts.faded}

## Get Started

## For Production or Single User
If setting up or running a production MSGalaxy service or creating your own personal MSGalaxy instance, use the latest release branch, which only receives stable code updates.

## Cloning new
If you do not have a MSGalaxy repository yet or you do not want to update the existing instance, run:
~~~
$ git clone -b release_17.09 https://github.com/galaxyproject/galaxy.git
~~~

## Updating exiting
If you have an existing MSGalaxy repository and want to update it, run:
~~~
$ git checkout release_17.09 && git pull --ff-only origin release_17.09
~~~

## For Development 
To obtain MSGalaxy for development, use the default branch after cloning: 'dev'. This is the branch that pull requests should be made against to contribute code (unless you are fixing a bug in a MSGalaxy release).
~~~
$ git clone https://github.com/galaxyproject/galaxy.git
~~~

## Start It Up 
MSGalaxy requires a few things to run: a virtualenv, configuration files, and dependent Python modules. However, starting the server for the first time will create/acquire these things as necessary. To start MSGalaxy, simply run the following command in a terminal window:
~~~
$ sh run.sh
~~~
This will start up the MSGalaxy server on localhost and port 8080. MSGalaxy can then be accessed from a web browser at http://localhost:8080. After starting, MSGalaxy's server will print output to the terminal window. To stop the MSGalaxy server, use Ctrl-C in the terminal window from which MSGalaxy is running. If galaxy does not start, you may be using the conda python. See the admin docs for more details.
To access MSGalaxy over the network, modify the 'config/galaxy.ini' file by changing the 'host' setting to
~~~
host = 0.0.0.0
~~~
Upon restarting, MSGalaxy will bind to any available network interfaces instead of the loopback.


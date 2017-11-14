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

## Next Steps
## Become an Admin
To control MSGalaxy through the UI (installing tools, managing users, creating groups, etc.), users must become an administrator. Only registered users can become admins. To give a user admin privileges, complete the following steps:
* Add the user's MSGalaxy login email to the configuration file 'config/galaxy.ini'. As shown here:
~~~
# this should be a comma-separated list of valid MSGalaxy users
admin_users = user1@example.com,user2@example.com
~~~
* If the file does not exist, copy it from the provided sample:
~~~
# cp config/galaxy.ini.sample config/galaxy.ini
~~~
* Restart MSGalaxy after modifying the configuration file for changes to take effect.
* Additional details can be found below.

# Install Tools
MSGalaxy comes with a small set of basic tools pre-installed. To install additional tools, follow the instructions on Installing tools into MSGalaxy from the Tool Shed.

# Troubleshooting
* Offline start: The initial MSGalaxy run requires Internet access to download the pre-built Python wheels of MSGalaxy's dependencies.
* The basic MSGalaxy install is a single-user instance and is only accessible by the local user. As with many web-based applications, enable cookies in the web-browser for full functionality.
* A common practice when using any web browser is to stay current with software updates to maximize performance and security. If moving forward to production server with login enabled, please make sure you and your end-users are current.
* Some tools shipped with MSGalaxy have dependencies that need to be satisfied manually. Please see details here.

# Shutting down MSGalaxy
Below are simplified instructions for shutting down local MSGalaxy server. If your configuration is more complicated, getting help from an administrator is recommended.

#The MSGalaxy process is running in the background
* If MSGalaxy was the last process running within a terminal window, bring it into the foreground with the command 'fg' and shut down with 'Ctrl-c'.
* If MSGalaxy is one of many processes running in the background within a terminal window, find it with the command jobs. The list of jobs will be numbered. Bring the Galaxy job to the foreground with the command 'fg <number_of_the_job>' and shut down with 'Ctrl-c'.
# xrdocs-scripts
How to setup docker-compose, and edit any XRdocs webpage live locally 

The docker-compose file runs your chosen repository (ex: programmability page) by running docker-compose up to start the locally hosted website on localhost:4000. To get it running with your choice of repository, create a new file called docker-compose.yml, and copy the contents of the file above. 

To get docker running, follow the docker installation guide for your system (insert link here). Once installed and tested, run "docker-compose up" in your terminal/command line and the jekyll website will launch on localhost:4000.

If it is your first time running the docker-compose file on your machine, it will take some time as it is pulling and installling dependencies. Once the installs are done, you will see a port host at the end of your command line

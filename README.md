# xrdocs-scripts
How to setup docker-compose, and edit any XRdocs webpage live locally 

The docker-compose file runs your chosen repository (ex: programmability page) by running docker-compose up to start the locally hosted website on localhost:4000. To get it running with your choice of repository, create a new file called docker-compose.yml, and copy the contents of the file above. 

To get docker running, follow the docker installation guide for your system (insert link here). Once installed and tested, run "docker-compose up" in your terminal/command line and the jekyll website will launch on localhost:4000.

If it is your first time running the docker-compose file on your machine, it will take some time as it is pulling and installling dependencies. Once the installs are done, you will see a port host at the end of your command line

If you recieve this error instead of a host, run "bundle add webrick"
<img width="1141" alt="Screenshot 2023-06-28 at 7 48 05 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/95593c70-3fdc-4622-ab90-6b151b567bae">

If you get this error instead, run "sudo gem install bundler:2.3.25" or whichever version of bundler it shows. Then run "bundle add webrick"
<img width="1221" alt="Screenshot 2023-06-28 at 7 51 41 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/8b534f38-2f0a-4fec-b737-7ab631548cfd">

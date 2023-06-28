# Getting Started with Local Development for XRdocs
How to setup docker-compose, and edit/preview any XRdocs webpage locally with live changes

The docker-compose file runs your chosen repository (ex: programmability) by running docker-compose up to start the locally hosted website on localhost:4000. To get it running with your choice of repository, create a new file called docker-compose.yml, and copy the contents of the file above. 

To get docker running, follow the docker installation guide for your system ([Docker Mac Install](https://docs.docker.com/desktop/install/mac-install/)). Once installed and tested, run "docker-compose up" in your terminal/command line and the jekyll website will launch on localhost:4000.

If it is your first time running the docker-compose file on your machine, it will take some time as it is pulling and installing dependencies. Once the installs are done, you will see a port host at the end of your command line

If you recieve this error instead of a host, run "bundle add webrick"
<img width="1141" alt="Screenshot 2023-06-28 at 7 48 05 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/95593c70-3fdc-4622-ab90-6b151b567bae">

If you get this error instead, run "sudo gem install bundler:2.3.25" or whichever version of bundler it shows. Then run "bundle add webrick"
<img width="1221" alt="Screenshot 2023-06-28 at 7 51 41 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/8b534f38-2f0a-4fec-b737-7ab631548cfd">

Once everything is installed, you can run "docker-compose up", the following will show in your terminal if successful
<img width="916" alt="Screenshot 2023-06-28 at 7 55 39 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/c3885781-e999-4936-997e-bacd29c9a06f">

You can also check in the docker desktop app, and see the container and images running.
<img width="1020" alt="Screenshot 2023-06-28 at 7 56 03 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/122f967c-4d9e-4c8b-a324-6be7abffbabd">

Once you open the link, you will be greeted with the webpage that you have chosen to edit (in this example, I have opened the programmability webpage)
<img width="1440" alt="Screenshot 2023-06-28 at 7 58 22 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/390b9347-847f-4097-8fb7-f51d6e6ab8a8">

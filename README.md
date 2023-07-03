# Getting Started with Local Development for XRdocs
How to setup a local environment to edit XRdocs and view changes before pushing

There are two ways to set this up, using a docker run command (recommended), or adding a docker-compose file into each clone repo locally.

The best way to set everything up for local edits would be to ensure that you have all of the repositories that you want to edit in a desginated folder such as "xrdocs" located on your device. (Here I have a folder created on my Desktop called XRdocs github, with repo's that have been cloned via git)
<img width="920" alt="Screenshot 2023-07-03 at 7 51 42 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/f2b6df41-64a0-4aca-b419-e5046b372f63">

The steps are as follows:
  1. Ensure that you have git downloaded on your system [Git install guide](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
  2. Create a folder and clone the repositories into your folder system
  3. Download any IDE of your choice
  4. Download Docker for your operating sysyem [Docker Mac Install](https://docs.docker.com/desktop/install/mac-install/), [Docker Windows Install](https://docs.docker.com/desktop/install/windows-install/)
  5. Run the test command for Docker (docker run hello-world) to ensure it is running properly
  6. Change your directory into whatever part of the webiste you want to work on (Ex: programmability)
  7. Once inside, you should be able to run the command listed (docker run --volume="$PWD:/srv/jekyll" -p 4000:4000 jekyll/jekyll:4.0 jekyll serve). After running, dependencies will be fetched and after a minute or so you will see a link to your locally hosted website
  8. If you want to see the Docker run in the Docker Desktop App, you can open it and will see it temporarily running 

# Compose File Method
The second method of setting up is a way to create a designated container for each repo you choose to edit rather than just a run command. Follow all of the above steps except for the Docker run command. Once completed, follow the steps below
  1. Create a file called docker-compose.yml. To get it running with your choice of repository, copy the contents of the file above.
  2. Once added, save the file and in your terminal run the command (docker-compose up). After dependencies, you should see this <img width="916" alt="Screenshot 2023-06-28 at 7 55 39 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/c3885781-e999-4936-997e-bacd29c9a06f">
  3. If you want to check the container as well, you can check now in the Docker Desktop and will see a designated container for your repo (ex: programmability) <img width="1020" alt="Screenshot 2023-06-28 at 7 56 03 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/122f967c-4d9e-4c8b-a324-6be7abffbabd">


If it is your first time running the docker-compose file on your machine, it will take some time as it is pulling and installing dependencies. Once the installs are done, you will see a port host at the end of your command line

If you receive this error instead of a host, run "bundle add webrick"
<img width="1141" alt="Screenshot 2023-06-28 at 7 48 05 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/95593c70-3fdc-4622-ab90-6b151b567bae">

If you get this error instead, run "sudo gem install bundler:2.3.25" or whichever version of bundler it shows. Then run "bundle add webrick"
<img width="1221" alt="Screenshot 2023-06-28 at 7 51 41 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/8b534f38-2f0a-4fec-b737-7ab631548cfd">

Once everything is installed, you can run "docker-compose up", the following will show in your terminal if successful
<img width="916" alt="Screenshot 2023-06-28 at 7 55 39 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/c3885781-e999-4936-997e-bacd29c9a06f">

Once you open the link, you will be greeted with the webpage that you have chosen to edit (in this example, I have opened the programmability webpage)
<img width="1440" alt="Screenshot 2023-06-28 at 7 58 22 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/390b9347-847f-4097-8fb7-f51d6e6ab8a8">

# Editing live
After opening the local host site, you are now able to edit anything via an IDE (using VScode in this example)
<img width="1440" alt="Screenshot 2023-06-29 at 9 48 41 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/814ed0cd-99b2-407d-98eb-66efedc8a7b3">

Here we are editing the blog article of "Getting started with gNMI".

As you edit the file, once you are done with your changes and want to see them live, save the file you are working on locally. Once you save, you will see Jekyll refresh the website in your terminal
<img width="535" alt="Screenshot 2023-06-29 at 9 53 36 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/584d0d31-13af-43af-af8e-85bf2a65a412">

Once Jekyll has reloaded, simply refresh the local webpage and you will see your changes visible
<img width="1440" alt="Screenshot 2023-06-29 at 9 54 29 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/72ca8655-1b77-48e7-a7cd-0a0089ab875e">

If you have to edit more, the same process follows. Edit the file, save changes, and refresh webpage.

Once you are satisfied with the changes, you can simply run "docker-compose stop" or on mac, use "ctrl + c" to end the local webpage. After, you can push your changes to github in the respective repository, and your changes will load live on github pages.


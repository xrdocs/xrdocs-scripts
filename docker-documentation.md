# Getting Started with Local Development for XRdocs
How to setup a local environment to edit XRdocs and view changes before pushing

There are two ways to set this up, using a docker run command (recommended), or adding a docker-compose file into each clone repo locally.

The best way to set everything up for local edits would be to ensure that you have all of the repositories that you want to edit in a designated folder such as "xrdocs" located on your device. (Here, I have a folder created on my Desktop called XRdocs GitHub, with repos that have been cloned via git)
<img width="946" alt="Screenshot 2023-08-15 at 10 46 19 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/02636ac0-9b44-456e-b451-92b38be34af5">

The steps are as follows:
-
  1. Ensure that you have git downloaded on your system [Git install guide](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
  2. Create a folder and clone the repositories into your folder system
  3. Download any IDE of your choice
  4. Download Docker for your operating system [Docker Mac Install](https://docs.docker.com/desktop/install/mac-install/), [Docker Windows Install](https://docs.docker.com/desktop/install/windows-install/)
  5. Run the test command for Docker (docker run hello-world) to ensure it is running properly
  6. Change your directory into whatever part of the website you want to work on (Ex: programmability)
  7. Once inside, you should be able to run the command listed (docker run --volume="$PWD:/srv/jekyll" -p 4000:4000 jekyll/jekyll:4.0 jekyll serve), for windows (docker run --volume="${PWD}:/srv/jekyll" -p 4000:4000 jekyll/jekyll:4.0 jekyll serve). After running, dependencies will be fetched, and after a minute or so, you will see a link to your locally hosted website

<img width="1091" alt="Screenshot 2023-08-15 at 11 10 43 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/0446710f-9ea4-4386-97b3-8189839ff592">


  8. If you want to see the Docker run in the Docker Desktop App, you can open it and will see it temporarily running
<img width="1254" alt="Screenshot 2023-08-15 at 11 11 52 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/b9d37ac5-6d9f-48f1-9105-5063c1855f6e">

One thing to note is that running with this command will show you the container it has created on the Docker Desktop application, and it will create a new container each time the command is rerun. However, since the container is just used to edit and then push to Github, you can delete the containers once you are done with your changes. 

# Compose File Method
The second method of setting up is a way to create a designated container for each repo you choose to edit rather than just a run command. Follow all of the above steps except for the Docker run command. Once completed, follow the steps below

  1. Create a file called docker-compose.yml in your local repo. To get it running with your choice of repository, copy the contents of the file above.
  2. Once added, save the file, and in your terminal, run the command (docker-compose up). After dependencies, you should see this

<img width="1091" alt="Screenshot 2023-08-15 at 11 10 43 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/0446710f-9ea4-4386-97b3-8189839ff592">

  4. If you want to check the container as well, you can check now in the Docker Desktop and will see a designated container for your repo (ex: programmability)
     
<img width="725" alt="Screenshot 2023-08-15 at 11 12 26 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/35e07bd5-9af2-4d20-a462-491e3bffd000">

One thing to note with this method is that whenever you finish editing changes and want to push to the origin, you will constantly have to remove and add this compose file into each repo locally. It is recommended to follow the docker run method instead.

# Troubleshooting 
If you get this error, make sure that you have ruby downloaded (ruby -v). Then if a version appears, run "bundle add webrick" and retry. If you keep getting an error, run "sudo gem install bundler:2.3.25" or for windows run "gem install bundler" or whichever version of bundler it shows, then run "bundle add webrick" and retry 
<img width="1206" alt="Screenshot 2023-06-28 at 7 50 16 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/6ff0ecfd-011e-4c4c-98dc-1b27ddbce5e3">

You should see the following in your terminal once successful

<img width="498" alt="Screenshot 2023-08-15 at 11 02 52 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/75a38fd5-06be-47ed-a206-69ddab570b81">

Once you open the link, you will be greeted with the webpage that you have chosen to edit (in this example, I have opened the programmability webpage)
<img width="1440" alt="Screenshot 2023-08-15 at 11 04 51 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/ef96d720-fda1-4240-bfd0-d17e4cd1033b">


# Editing live
After opening the local host site, you are now able to edit anything via an IDE (using VScode in this example). Here we are editing the blog article of "Getting started with gNMI".

<img width="1440" alt="Screenshot 2023-07-05 at 7 35 06 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/df7cbce4-188b-417f-95e3-8316dc39c4b8">

As you edit the file, once you are done with your changes and want to see them live, save the file you are working on locally. Once you save, you will see Jekyll refresh the website in your terminal

<img width="1440" alt="Screenshot 2023-08-15 at 11 08 20 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/f7e3b993-7be7-4ba8-953d-179555d61888">

Once Jekyll has reloaded, simply refresh the local webpage and you will see your changes visible. Here we can see that the green highlights in our IDE indicate the changes we have made onto our webpage

<img width="1440" alt="Screenshot 2023-08-15 at 11 09 11 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/7e4fc8ab-1b57-4887-bf03-cf8039099e55">

Once you are satisfied with the changes, you can simply run do "ctrl + C" on mac or close the terminal to end the local webpage. After, you can push your changes to github in the respective repository, and your changes will load live on github <img 
pages. Sometimes your local IDE will show lots of changes being pushed to github, which were all done when dependencies were being updated alongside with the changes that you have made. Just make sure the changes you have made are visible and you can push to Github

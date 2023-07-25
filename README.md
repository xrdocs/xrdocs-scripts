# Getting Started with Local Development for XRdocs
How to setup a local environment to edit XRdocs and view changes before pushing

There are two ways to set this up, using a docker run command (recommended), or adding a docker-compose file into each clone repo locally.

The best way to set everything up for local edits would be to ensure that you have all of the repositories that you want to edit in a designated folder such as "xrdocs" located on your device. (Here, I have a folder created on my Desktop called XRdocs GitHub, with repos that have been cloned via git)
<img width="920" alt="Screenshot 2023-07-03 at 7 51 42 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/f2b6df41-64a0-4aca-b419-e5046b372f63">

The steps are as follows:
  1. Ensure that you have git downloaded on your system [Git install guide](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
  2. Create a folder and clone the repositories into your folder system
  3. Download any IDE of your choice
  4. Download Docker for your operating system [Docker Mac Install](https://docs.docker.com/desktop/install/mac-install/), [Docker Windows Install](https://docs.docker.com/desktop/install/windows-install/)
  5. Run the test command for Docker (docker run hello-world) to ensure it is running properly
  6. Change your directory into whatever part of the website you want to work on (Ex: programmability)
  7. Once inside, you should be able to run the command listed (docker run --volume="$PWD:/srv/jekyll" -p 4000:4000 jekyll/jekyll:4.0 jekyll serve), for windows (docker run --volume="${PWD}:/srv/jekyll" -p 4000:4000 jekyll/jekyll:4.0 jekyll serve). After running, dependencies will be fetched, and after a minute or so, you will see a link to your locally hosted website
<img width="515" alt="Screenshot 2023-07-06 at 8 26 08 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/2cd16777-df6a-412d-8c65-c509fe7b4756">


  8. If you want to see the Docker run in the Docker Desktop App, you can open it and will see it temporarily running
<img width="1022" alt="Screenshot 2023-07-06 at 8 26 44 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/f6113802-c6c4-4e72-99d3-22bd93d7ff57">

One thing to note is that running with this command will show you the container it has created on the Docker Desktop application, and it will create a new container each time the command is rerun. However, since the container is just used to edit and then push to Github, you can delete the containers once you are done with your changes. 

# Compose File Method
The second method of setting up is a way to create a designated container for each repo you choose to edit rather than just a run command. Follow all of the above steps except for the Docker run command. Once completed, follow the steps below
  1. Create a file called docker-compose.yml in your local repo. To get it running with your choice of repository, copy the contents of the file above.
  2. Once added, save the file, and in your terminal, run the command (docker-compose up). After dependencies, you should see this <img width="916" alt="Screenshot 2023-06-28 at 7 55 39 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/c3885781-e999-4936-997e-bacd29c9a06f">
  3. If you want to check the container as well, you can check now in the Docker Desktop and will see a designated container for your repo (ex: programmability) <img width="1020" alt="Screenshot 2023-06-28 at 7 56 03 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/122f967c-4d9e-4c8b-a324-6be7abffbabd">

One thing to note with this method is that whenever you finish editing changes and want to push to the origin, you will constantly have to remove and add this compose file into each repo locally. It is recommended to follow the docker run method instead.

# Troubleshooting 
If you receive this error instead of a host, run "bundle add webrick" and retry
<img width="1141" alt="Screenshot 2023-06-28 at 7 48 05 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/95593c70-3fdc-4622-ab90-6b151b567bae">

If you get this error, run "sudo gem install bundler:2.3.25" or whichever version of bundler it shows, then run "bundle add webrick" and retry 
<img width="1221" alt="Screenshot 2023-06-28 at 7 51 41 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/8b534f38-2f0a-4fec-b737-7ab631548cfd">

You should see the following in your terminal once successful
<img width="916" alt="Screenshot 2023-06-28 at 7 55 39 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/c3885781-e999-4936-997e-bacd29c9a06f">

Once you open the link, you will be greeted with the webpage that you have chosen to edit (in this example, I have opened the programmability webpage)
<img width="1440" alt="Screenshot 2023-06-28 at 7 58 22 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/390b9347-847f-4097-8fb7-f51d6e6ab8a8">

# Editing live
After opening the local host site, you are now able to edit anything via an IDE (using VScode in this example). Here we are editing the blog article of "Getting started with gNMI".

<img width="1440" alt="Screenshot 2023-07-05 at 7 35 28 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/fae3524d-8245-4650-b220-4da943c7b843">

As you edit the file, once you are done with your changes and want to see them live, save the file you are working on locally. Once you save, you will see Jekyll refresh the website in your terminal

<img width="535" alt="Screenshot 2023-06-29 at 9 53 36 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/584d0d31-13af-43af-af8e-85bf2a65a412">

Once Jekyll has reloaded, simply refresh the local webpage and you will see your changes visible. Here we can see that the green highlights in our IDE indicate the changes we have made onto our webpage

<img width="1440" alt="Screenshot 2023-06-29 at 9 54 29 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/72ca8655-1b77-48e7-a7cd-0a0089ab875e">

Once you are satisfied with the changes, you can simply run do "ctrl + C" on mac or close the terminal to end the local webpage. After, you can push your changes to github in the respective repository, and your changes will load live on github pages. Sometimes your local IDE will show lots of changes being pushed to github, which were all done when dependencies were being updated alongside with the changes that you have made. Just make sure the changes you have made are visible and you can push to Github


<img width="218" alt="Screenshot 2023-07-06 at 8 21 10 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/934c7d96-80f4-4cd2-8ead-0ed155b3a744">


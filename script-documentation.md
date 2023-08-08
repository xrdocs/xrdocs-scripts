# Fetching latest blogs/articles for xrdocs.io
There are 3 different steps for retrieving the latest blogs and displaying them onto the homepage of xrdocs. 
* A python script (fetch_blogs.py) that fetches all the contents from every repo located under the xrdocs github using the github API. We are using a PAT key that is stored under secret variables under the organization. This script outputs a JSON file containing all of the article names, links, and descriptions, only if the articles are published, and if their positon : top. The script is stored along with the JSON file in xrdocs/xrdocs-scripts
* A github action that runs daily, to check if there are newer articles that have been added, if there are, a new JSON file is pushed and committed, if not the action exits automatically. The github action runs in the xrdocs-scripts repo, where the python script and JSON file are stored
* A javascript script that fetches the contents of our JSON file, and formats them to our div elements so that all posts have the same clean format on the xrdocs homepage. The javascript is stored under the xrdocs/xrdocs.github.io/_layouts/splash.html 


# Maintaining Python script for fetching latest blogs/articles
When a new repository or webpage is created for xrdocs, you will have to manually add the directory and repository in the python script so it can fetch the articles, only add the _blogs and _tutorials folders. 

<img width="625" alt="Screenshot 2023-08-08 at 8 02 56 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/1429d126-bdfe-4c03-a57c-7c9ea5abf7ff">

You can add the new repository here following the same format 

One thing to note is that the script excludes a specific file from the xrdocs/design/_blogs repo, with the blog title of 2019-02-02-modernizing-ixp-design.md, as it contains a YAML error inside the article itself. If this case is ever removed from the script, it will fail as it cannot succesfully parse through the directories if any markdown files contain issues. 

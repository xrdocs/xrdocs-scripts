# Fetching latest blogs/articles for xrdocs.io
There are 3 different steps for retrieving the latest blogs and displaying them onto the homepage of xrdocs. 
* A python script (fetch_blogs.py) that fetches all the contents from every repo located under the xrdocs github using the github API. We are using a PAT key that is stored under secret variables under the organization. This script outputs a JSON file containing all of the article names, links, and descriptions, only if the articles are published, and if their positon : top
* A github action that runs daily, to check if there are newer articles that have been added, if there are, a new JSON file is pushed and committed, if not the action exits automatically. The github action runs in the xrdocs-scripts repo, where the python script and JSON file are stored
* A javascript script that fetches the contents of our JSON file, and formats them to our div elements so that all posts have the same clean format on the xrdocs homepage. The javascript is stored under the xrdocs/xrdocs.github.io/_layouts/splash.html 


# Maintaining Python script for fetching latest blogs/articles


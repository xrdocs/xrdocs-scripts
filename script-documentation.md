# Fetching latest blogs/articles for xrdocs.io
There are 3 different steps for retrieving the latest blogs and displaying them onto the homepage of xrdocs. 

- A python script (fetch_blogs.py) that fetches all the contents from every repo located under the xrdocs github using the github API. We are using a PAT key that is stored under secret variables under the organization. This script outputs a JSON file containing all of the article names, links, and descriptions, only if the articles are published, and if their positon : top. The script is stored along with the JSON file in xrdocs/xrdocs-scripts
  
* A github action that runs daily, to check if there are newer articles that have been added, if there are, a new JSON file is pushed and committed, if not the action exits automatically. The github action runs in the xrdocs-scripts repo, where the python script and JSON file are stored
  
* A javascript script that fetches the contents of our JSON file, and formats them to our div elements so that all posts have the same clean format on the xrdocs homepage. The javascript is stored under the xrdocs/xrdocs.github.io/_layouts/splash.html
  
* **It is important to note that if you want the blog to be shown under this section, both the position : top, and published : true, have to be there**


# Maintaining Python script for fetching latest blogs/articles
When a new repository or webpage is created for xrdocs, you will have to manually add the directory and repository in the python script so it can fetch the articles, only add the _blogs and _tutorials folders. 

<img width="625" alt="Screenshot 2023-08-08 at 8 02 56 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/1429d126-bdfe-4c03-a57c-7c9ea5abf7ff">

You can add the new repository here following the same format.

* One thing to note is that the script excludes a specific file from the xrdocs/design/_blogs repo, with the blog title of 2019-02-02-modernizing-ixp-design.md, as it contains a YAML error inside the article itself. If this case is ever removed from the script, it will fail as it cannot succesfully parse through the directories if any markdown files contain issues. 

# Adding new user for github actions
If you need to add a new user, a new PAT token has to be created under the new user and has to be added under the secret key:
* Navigate to github and your account settings, and under developer settings and personal access token, create a new Token(classic). Once you generate this, do not close this tab until you are the done with the following steps, as the token is only shown once
* Copy the token, and navigate to [xrdocs organization settings](https://github.com/organizations/xrdocs/settings/secrets/actions). Once there, you will see an Action secret called FETCH_BLOGS, you must edit this value and enter your token as the new value, once done this ensures that the new token will be used when running the github actions and fetching from the github API. You will now recieve updates when the github action runs daily and when it is successful or fails

This token is stored under the secret key so that anyone viewing the script and the github action isn't able to see under what user we are fetching the github API from. The key is also inputted into the script and the action as shown below, so the only thing that ever needs to be changed is the token stored inside of the secret key. The github action code is stored at [Github action](https://github.com/xrdocs/xrdocs-scripts/blob/main/.github/workflows/fetch_latest_blogs.yml). 

<img width="518" alt="Screenshot 2023-08-08 at 8 31 00 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/10bd62e5-2e0c-4aad-a7d5-8b2b45287ba4">
<img width="455" alt="Screenshot 2023-08-08 at 8 32 50 AM" src="https://github.com/xrdocs/xrdocs-scripts/assets/52422516/1c1e1b3e-c5aa-4151-891f-121eabcb8460">

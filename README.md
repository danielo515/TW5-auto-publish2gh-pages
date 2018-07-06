# [TW5 2 Github pages](https://github.com/danielo515/TW5-auto-publish2gh-pages)

We all love Github pages. They are an easy,reliable and cheap way to host static sites. [TiddlyWiki](tiddlywiki.com) is a single page web application wiki that can be hosted as a single html file. It is an awesome unique application, and I strongly recommend you to check it out at [TiddlyWiki.com](tiddlywiki.com). The problem with it is that there is not an easy fast way to host a tiddlywiki file on github pages... until now. 

This repository is **both a template and a set of instructions** to host a tiddlywiki on your own Github pages repository. Following this instructions you will be able to have your own wiki up and runing in less than 10 minutes **without** any `git` or Github Knowledge and **without installing** any software on your computer.

Using this work-flow has several advantages:
1. Github pages are absolutely **free** and reliable
2. Tiddlers are built from **individual `.tid` files**
3. Built in **changes history and diff**
4. Github allows you to edit and add files directly from their web interface, so you don't have to install anything in your computer.
3. No `git` or Github Knowledge required


<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
# Table of Contents

- [Requisites](#requisites)
- [First time setup](#first-time-setup)
  - [Github setup](#github-setup)
  - [Creating the first wiki](#creating-the-first-wiki)
- [Creating another wiki](#creating-another-wiki)
- [Editing tiddlers](#editing-tiddlers)
  - [Prose](#prose)
  - [Dilinger](#dilinger)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Requisites
The list of pre-requisites is quite small, and you only need to fit them once
* A [Github](https://github.com) account
* A [Travis-ci](https://travis-ci.org/ "go to travis site") account

# First time setup
This are the steps required for the first time setup. Once you have completed all the steps listed here for the first time it will be much faster to just add new wikis.
## Github setup
1. We have to create a `Personal access token` to allow our publish scripts to push to our github account. This is only needed on the first time setup. Go to [Github's tokens management page](https://github.com/settings/tokens)
2. Create a new token clicking on `Generate new token`
3. Provide a meaningful token description. **This is very important** because it will be the only clue you will have to identify the token usage.
4. Make sure `repo` and `public_repo` options are selected
5. Click on `Generate token`. Here is an overview of this step:
![Generate token](/../screenshots/github-token.png?raw=true)
6. Github will generate an unique token. **Take note of it now because you will not have any other opportinity!!**

## Creating the first wiki
1. Fork this repository. This step will be necessary on every new wiki. As I have promised  you can do this directly from Github, just click the Fork button on the top righ corner of this repository page:
![Fork button](/../screenshots/fork.png?raw=true "Fork button")
2. Once you have forked the repository, you can rename it to fit your needs.
2.  Go to [Travis-ci](https://travis-ci.org/ "go to travis site") and sign in using your github account.
3. If this is the first time you are using Travis just authorize the application to access your github account.
2. Once you have accessed your Travis account you will be directed to your dashboard.
3. On the left side of your dashboard you should have a list of the repositories under Travis management. At the first time this list should be empty.
4. Click the plus sign next to `My Repositories` to put the forked repository under Travis management:
![Add Repository](/../screenshots/Travis-CI_addRepo.png?raw=true "Add repo")
5. You will be redirected to your profile. Here you have to locate the repository you have just forked and activate the "switch" to put it under Travis management. This should be easy because Travis provides an explanatory screen shot.
6. If you don't find the repository you are looking for, click the `Sync` button to refresh the list of repositories:
![Add Repository](/../screenshots/Travis-CI_sync.png?raw=true "Add repo")
7. In our example we are activating this Github repository:
![Activate Repository](/../screenshots/Travis-CI_activate.png?raw=true)
8. Now it's time to setup the global variables required by our build scripts. To do so click on the gear icon next to the "activate" switch:
![config Repository](/../screenshots/Travis-CI_config.png?raw=true)
11. You should be now at the Settings page of the repository. Leave the General settings as they are by default.
12. On the Environment Variables section We are going to add the required variables.
    1. First add `GH_REF`, which is the url of **your forked repository without the https prefix and with a `.git` extension. For this variable you can set to `on` the `Display value in build log`, so you can check that it is correct on every build. Click add
    ![first variable](/../screenshots/Travis-CI_GH_REF.png?raw=true)
    2. Follow the same process to add the `GH_TOKEN` variable, but this time make sure that `Display value in build log` is set to off for security reasons. Paste here the Github **token we have generated previously**:
    ![Token variable](/../screenshots/Travis-CI_GH_TOKEN.png?raw=true)
    3. Follow the exact same process to add `GH_EMAIL` variable. This should be the email you have used to register your account on github. After this process you should see something like this:
    ![Variables Setup](/../screenshots/Travis-CI_Variables.png?raw=true)
    4. Changes are saved **automatically** so at this point we are done with configuration and can switch to `current` tab.
13. Switch to `current` tab to see what is going on during build process. The build process happens **every time you push a change to your repository** and not before. An ongoing build looks like this:
![Building](/../screenshots/Travis-CI_Building.png?raw=true)
14. Now you are ready to go. Edit any file or create any new file **your forked repository** and push the changes to trigger a build. You can do this directly from Github. For more details about this process see the [`Editing tiddlers` section](#editing-tiddlers)
15. Once the build **has finished successfully** you can just visit `<your-git-username>.github.io/your-repo-name` to see the results of your build

# Creating another wiki
Once you have completed the first time setup, it is much easier to setup another wiki. Here is a summary of the required Steps:
1. Fork this repository: 
![Fork button](/../screenshots/fork.png?raw=true "Fork button")
2. Rename the repository to fit your needs.
3.  Go to [Travis-ci](https://travis-ci.org/ "go to travis site") and sign in using your github account.
4. On the left side of your dashboard click the plus sign next to `My Repositories` to put the forked repository under Travis management:
![Add Repository](/../screenshots/Travis-CI_addRepo.png?raw=true "Add repo")
5. Locate the repository **you have just forked** and activate the "switch" to put it under Travis management.
6. If you don't find the repository you are looking for, click the `Sync` button to refresh the list of repositories:
![Add Repository](/../screenshots/Travis-CI_sync.png?raw=true "Add repo")
7. Setup the global variables
8. Edit/add the required tiddlers and make a push. This can be done directly on github.

# Editing tiddlers
You can just edit or add new tiddlers directly on github, which is quite comfortable, or you can use a markdown editor. Tiddlywiki sintax is not exactly markdown, but it is close enough to use it as a small reference and markdown editors usually helps you completing lists and provide preview.

I recommend you to use prose, which is the tool I have used to edit this README:

## Prose
1. visit https://prose.io/
2. You have to link it to github, so you can edit and save the files on your repository
3. Click on `Authorize aplication` and authorize it on Github
4. Once you have authorized the application you can start creating and editing tiddlers:
   1. Select the repository of your wiki
   2. Navigate to `wiki`>`tiddlers` directory
   3. Select the tiddler you want to edit or create a new file. **If you create a new file make sure** you give it a `.tid` extension.
   4. Once you  have your "tiddler ready" click the save icon. You can provide a commit message if you want.


## Dilinger
To edit markdown files you have a better alternative which is dillinger. The drawback of dilinger is that it only recognices `.md` files:

1. visit https://dillinger.io/
2. You can link it to github, so you can edit and save the files on your repository
3. To be able to save to github, you have to first import the tiddler you want to edit from there. The first time you will have to authorize the application:
   1. Click on `IMPORT FROM` 
   2. On the drop down select `Github`
   3. Authorize the application if needed
   4. Select the repository you want to edit, and select the master branch
   5. Navigate to `wiki`>`tiddlers` directory
   6. Select the tiddler you want to edit
4. Once you  have your "tiddler ready" click `SAVE TO` and select github

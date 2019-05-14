# Pushing your games to the Github repository

You've spent the last day or so hacking around with PyGlet, making games. Now you are going to use Git to push your games onto the main Github project page so that the TMCS-2019 Github repository contains a record of what you have done.

To do this you are each going to need a Github username, which [you can set up here](https://github.com/), and which you will provide to the course instructor, so that they can give you temporary permissions to contribute to the TMCS-2019 Github project. 

To get started, you will need to clone the TMCS-2019 repository onto your own computer. There is a [10-part series of videos from the entertaining Daniel Schiffman](https://www.youtube.com/playlist?list=PLRqwX-V7Uu6ZF9C0YMKuns9sLDzK6zoiV) which I highly recommend because they provide a superb intro to Git and Github. For now though, I am going to recommend [that you watch video 1.6](https://www.youtube.com/watch?v=yXT1ElMEkW8&list=PLRqwX-V7Uu6ZF9C0YMKuns9sLDzK6zoiV&index=6). Specifically, this video (from 4:42) explains how to clone a Github repository to your computer.

I usually like to keep all of my GIT projects in a single directory called GIT-repos, so that I can easily keep track of the various projects to which I'm contributing. Make a GIT-repos directory, and then follow the instructions in the Schiffman video 1.6 to clone the TMCS-2019 repository into GIT-repos.

Once you've cloned TMCS-2019 onto your own machine, you can inspect its contents. You will see that it contains a folder called studentProjects.

Each of you should add to the studentProjects directory a folder whose title is firstnameSurname (so for example, I would name this folder davidGlowacki). Place within the firstnameSurname folder all of the *.py source files required to run your game from pyCHARM. 

Once you've placed the files in the directory, you need to tell GIT that it should consider these new files to be part of the repository. From within the firstnameSurname directory, you can do this with the command

git add --all

Once you've added your files, follow the instructions in the Schiffman video, and carry out the following sequence of steps: 
(1) git commit your changes to your local TMCS-2019 repository
(2) do a git pull, ensuring that any changes which others may have made to the remote TMCS-2019 Github master repository are merged with changes in your local repository
(3) do a git push, so that your (merged) local repository shows up in the remote TMCS-2019 Github master repository

You can determine whether you have managed to push your changes to the remote TMCS-2019 Github master repository by inspecting [the TMCS-2019/studentProjects folder](https://github.com/davidglo/TMCS-2019/tree/master/studentProjects). If you've done it correctly, you should see that your firstnameSurname folder, which contains the appropriate files required to run your game.

If you'd like to make any more changes to your files, you can do so by following steps (1) - (3) above.

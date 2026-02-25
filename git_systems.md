# Git Systems 

For version controlled documenting. These instructions are not for collabortating, this is only for solo use (for now) 

## Set up 

Go to <https://github.com> and create an account. 

Create repositories (repos) for each of your projects. Repos can be public or private. 

To link your repos with your local set up, navigate to the location you want to store your repo in your terminal and type: 

`git clone git@github.com:username/repo-name.git`

`cd repo name`

### Some useful commands to work with git locally 

`git pull` - pulls anything new to your your current workspace, useful if you work on multiple computers 

`git add .` - adds all changed files 

`git add filename` - adds filename specifically 

`git commit -m "your commit message here"` - 'commiting' the added files to git 

`git push` - pushes all added files to the remote repo, now these files can be accessed from the web. 


Each time you commit you leave a message to your future self of what you changed. Then at the end of the day/session you push all of the commits to store them in git. 
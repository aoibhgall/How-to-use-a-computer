# Git Systems 

For version controlled documenting. These instructions are not for collabortating, this is only for solo use (for now) 

## Set up 

Go to <https://github.com> and create an account. 

Create repositories (repos) for each of your projects. Repos can be public or private. 

To link git hub to your machine you need to first install git. this can be done via a desktop app or using Homebrew or command line tools. 

Then you need to create an ssh key. 

### Configure your Git identity 

In the terminal

`git config --global user.name "Your Name"`
`git config --global user.email "your@email.com"`


*It might be useful, if you've done this before you can check on your old machine what your credentials are with*

`git config --global --list`

### Generate SSH key 

run in terminal 

`ssh-keygen -t ed25519 -C "your@email.com"` 

you can create a passphrase here then if you like. 

### SSH agent

run `eval "$(ssh-agent -s)"`

Then add the key `ssh-add ~/.ssh/id_ed25519`

copy the public key `pbcopy < ~/.ssh/id_ed25519.pub`

### Add the key to GitHub

1. open [GitHub](https://github.com)
2. log in 
3. go to Settings 
4. go to ssh and gpg keys 
5. new ssh key 
6. paste the key and save 


You can then test the connection with `ssh -T git@github.com`, type `yes` then you should see `Hi username! You've successfully authenticated`

### Clone repos

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

#### Git Ignore 

If you want git to ignore any files or file types. 

Create a file in your repo named `.gitignore` *I normally just make this with vim in the terminal*

*vim notes coming soon* 

The content of the gitignore file is just all the files you want git to ignore. 

For example 

- filename.py - specifically ignores this file
- *.png - ignores all files ending in .png


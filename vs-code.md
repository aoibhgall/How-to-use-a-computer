# Setting up VS code 

I use VS code for many things
- writing LaTeX documents 
- writing Python scripts 
- writing Markdown scripts (e.g. for this blog)

It's not always so clear how you set it up for these things 

## Initial set up 

Coming soon ..


Then VS code works seemlessly with Markdown and quite well with git repos. 

## Setting up VS code for LaTeX 

This is no easy task. Coming soon. 

## Setting up VS code for Python 

My preference for python programming would typically be Spyder, which is built for python, but it's not working as well for me on my mac as it used to on my windows machine. My goal is now to set up VScode for python in a spyder-similar set up. And to keep it smart with miniconda and proper environments. 

### Environments 

I'm using miniconda for my python programming and with this you can create environments. 

It is important to keep the `base` clean. 
So the desired set up is: 

- `base` - clean 
- `py` - environment for general daily use 
- `project_i` - environment for a specific project if needed. 

#### Create the `py` environment 

In the terminal, in the home directory 

`conda create -n py python=3.11` 

or whatever python version you like. 

To activate use 

`conda activate py`

to deactivate use 

`conda deactivate py` .

So now activate your environment. and you should see 

`(py)` instead of `(base)` in your terminal. 

#### Install necessary packages 

In `(py)` install the essentials 

`conda install numpy pandas matplotlib scipy`

Also possibily useful 

`conda install seaborn jupyter ipython` 

If a package isn't available by conda, pip can be used

`pip install package`

#### Connect VS code to `py` 

Open VS code from the activated environment 

`code .` - this opens vs code 

##### Setiing `py` as the global default interpreter



1. `Cmd + Shift + P` - opens Command Palette
2. Go to **Preferences: Open User Settings (JSON)**
2. Add 

` {
    "python.defaultInterpreterPath": "/opt/miniconda3/envs/py/bin/python"
}`

*Check that this is the correct path, by going to* `Python:select Interpreter` *and copying the path that specifies your desired environment*

3. Then close the `json` file and quit VS code. 
4. Reopen VS code to check that the python interpreter is the correct one. 

##### Enable Automatic Terminal Activation 

Open settings `CMd + ,` 

Search Python > Terminal: Activate Environment - make sure this is checked. 

Now VS code is conected to the desired python environment. 




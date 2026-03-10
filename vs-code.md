# Setting up VS code 

I use VS code for many things
- writing LaTeX documents 
- writing Python scripts 
- writing Markdown scripts (e.g. for this blog)

It's not always so clear how you set it up for these things 

## Initial set up 

Coming soon ..


Then VS code works seemlessly with Markdown and quite well with git repos. 

## Useful VS code things 

`Cmd + Shift + P` opens the Command Palette.

`Cmd + K` then `Cmd + S` opens keyboard shortcuts. From here you can create your own keyboard shortcuts for things. 

`Cmd + ,` opens settings.

`Cmd + /` will comment highlighted block. (move this to python)

## Modifying preferences with `json`

In vscode you can update and set your preferences in the `json` file. 

To open the `json` file

`Cmd + Shift + P` and type Preferences: Open User Settings (JSON)

In this file you can add recipes (as we will see later in the setting up for latex section), defaults (python), and many other preferences. 

*I will try and add my json file to the repo and incllude some explanation fo what everything does*


## Setting up VS code for LaTeX 

This is no easy task. Coming soon. 

*This section isn't complete, but I will add stuff here as they arise for me*

#### Disabling Copilot AI for LaTeX (only)

add 

`"github.copilot.enable":{
    "*": true,
    "latex": false
}` 

to your json file.


## Setting up VS code for Python 

My preference for python programming would typically be Spyder, which is built for python, but it's not working as well for me on my mac as it used to on my windows machine. My goal is now to set up VScode for python in a spyder-similar set up. And to keep it smart with miniconda and proper environments. 

### Environments 

I'm using miniconda for my python programming and with this you can create environments. 

It is important to keep the `base` clean. 
So the desired set up is: 

- `base` - clean 
- `py` - environment for general daily use 
- `project_i` - environment for a specific project if needed. 

*Instructions on creating environments in python are in the python file*


### Extensions 

Important extensions for using Python in vs code are **Python, Pylance and Jupyter** (if you want jupyter notebook style programming). All subsequent necessary extensions should download and install with the installation of these extensions. 

#### Connect VS code to `py` 

Activate your environemt `conda activate py`

Open VS code, and open desired "workspace"

`Cmd + Shift + P` then navigate to **Select Python Interpreter**. Make sure you chose the Interpreter path that includes your new environment. 

(A workspace is any folder opened separately in a vs code window)

*This step needs to be completed for every new "workspace" you wish to use python in* (This is a vs code bug)

VS code should remember the Python interpreter for each workspace. 

*You can set your env to be the default, but vscode often ignores this - it can't hurt though* 

To ensure vscode activates your environment in the terminal navigaate to `Python > Terminal: Activate Environment` and check this box.

To set your `py` environment as Global Default Interpreter:

1. `Cmd + Shift + P` 
2. Preferences: Open User Settings (JSON)
3. Add `"python.defaultInterpreterPath": "/Users/YOUR_USERNAME/miniconda3/envs/py/bin/python"`

*Or just search Select Interpreter Path and copy that address*


##### Cells


If you want to use **Cells** in python in vscode you need to work with Jupyter. With this you  run in the *Interactive Window* but this is fairly intuative and works automatically on any `.py` file with cells. 

### Further Personalisation









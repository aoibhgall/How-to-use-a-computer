# Setting up VS code 

I use VS code for many things
- writing LaTeX documents 
- writing Python scripts 
- writing Markdown scripts (e.g. for this blog)

It's not always so clear how you set it up for these things 

## Initial set up 

Download and install [VScode](https://code.visualstudio.com/download)

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


# Setting up VS code for LaTeX 

Once you have TeX Live installed you can then set up vscode for latex. 

The most important thing is the Latex Workshop Extension. Go to Extensions and search Latex Workshop. 

To use latex without issues you need a couple of things

####  pdflatex, biber, bibtex 

add this to you settings json 

```
  "latex-workshop.latex.tools": [
    {
      "name": "pdflatex",
      "command": "pdflatex",
      "args": [
        "-synctex=1",
        "-interaction=nonstopmode",
        "-file-line-error",
        "%DOC%"
      ]
    },
    {
      "name": "biber",
      "command": "biber",
      "args": ["%DOCFILE%"]
    },
    {
      "name": "bibtex",
      "command": "bibtex",
      "args": ["%DOCFILE%"]
    }


  ],
```

this tells Latex Workshop about pdflatex, biber and bibtex, which are important for our compiling recipe. 

#### Latex recipes 

The most stable compiling recipe is pdflatex -> biber -> pdflatex ->pdflatex. 

I always ran into issues with the bibliography when I tried to use any other recipe. 

To execute this recipe in vscode everytime you want to compile, add the following to the settings json file 

```
  "latex-workshop.latex.recipes": [
    {
      "name": "pdflatex -> biber -> pdflatex*2",
      "tools": [
        "pdflatex",
        "biber",
        "pdflatex",
        "pdflatex"
      ]
    },
    {
      "name": "pdflatex -> bibtex -> pdflatex*2",
      "tools": [
        "pdflatex",
        "bibtex",
        "pdflatex",
        "pdflatex"
    ]
    }

  ],
```

This write the recipe, now we also need to add `"latex-workshop.latex.recipe.default": "pdflatex -> biber -> pdflatex*2",` to set it as the default, and `"latex-workshop.intellisense.citation.backend": "biblatex",` to cement biblatex for the bibliography.  

#### pfd preview 

If you want to use a side by side pdf preview and editor, add 
```
"workbench.editorAssociations": {
    "*.pdf": "default"
},
```
to json settings.



#### Disabling Copilot AI for LaTeX (only)

add 

`"github.copilot.enable":{
    "*": true,
    "latex": false
}` 

to your json file.

Once you've added all of your preferences, restart vscode and it should work. 


# Setting up VS code for Python 

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

## Further Personalisation

### Preamble 

To create a premable you need to use **Snippets**

1. Preferences: Configure User Snippets
2. python.json
3. add snippet 

My snippet 

```
{
  "Python Preamble": {
    "prefix": "pypreamble",
    "body": [
      "# -*- coding: utf-8 -*-",
      "\"\"\"",
      "Created on ${CURRENT_YEAR}-${CURRENT_MONTH}-${CURRENT_DATE} ${CURRENT_HOUR}:${CURRENT_MINUTE}",
      "",
      "@author: aoibhgall",
      "\"\"\"",
      "",
      "",
      "#%% importing essentials",
      "import numpy as np",
      "import scipy.sparse as sparse",
      "import scipy.sparse.linalg as slinalg",
      "import matplotlib",
      "matplotlib.use('TkAgg')",
      "import matplotlib.pyplot as plt",
      "import matplotlib.animation as animation",
      "",
      "",
      "#%%"
    ],
    "description": "Python scientific preamble"
  }
}
```









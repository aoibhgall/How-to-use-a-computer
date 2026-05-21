# Setting up and using Python locally 

## Installing Python with Miniconda


I like to use **Miniconda** to install python and packages. 

Go to [Miniconda](https://www.anaconda.com/docs/getting-started/miniconda/main) and download the **Command Line** version applicable to your machine. 

Then go to the terminal, navigate to Downloads 

`ls` should show something like `Miniconda3-latest-MacOSC-arm64.sh` 

run this file with bash 

`bash Miniconda3-latest-MacOSC-arm64.sh` 

and follow all the steps and agree to the license terms etc. 
Install miniconda in the default location and then say yes to initialization. 

restart the terminal

If the terminal prompt now starts with `(base)` conda is active. 

Check conda and python with 

`conda --version` and `python --version` both of these should return a version number. 

Then update conda 

`conda update -n base -c defaults conda` 


## Environments 

It's not very practical to install all packages into the base, so it's recommemded to create and work within **Environments**

I have one general python environment for most of my work, and then I create new specific environments when the project calls for it. 

### Creating Environments 

Open the Terminal and run 

`conda create -n py python=3.11`

`py` is the environment name, I chose py as my general python environment 

Activate the environment 

`conda activate py` 

*you should now see somthing like `(py) username@computer %`*

At this point you install core packages: numpy, matplotlib, scipy, jupyter, pandas, ipykernel

`pip install numpy matplotlib scipy jupyter pandas ipykernel`

Connect Python to jupyter 

`python -m ipykernel install --user --name py --display-name "Python (py)"`

Check environments with `conda env list`

# Using Python in Jupyter Notebooks 

Sometimes we can't always use python locally. 
For example, when we want to work with large data sets or our collaborators like to use Jupyter Notebooks. 

Jupyter Notebooks are a useful and powerfull tool for 
data science and analysis. Also they made presenting your work with code and plots and notes very easy. 

### Markdown with Jupyter

You can use Markdown cells along with coding to explain what's going on. Just select markdown at the top of the page where it says `Code` by default to turn on this setting. Then proceed with Markdown as normal. 


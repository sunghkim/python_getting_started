## python_getting_started
Step-by-step tutorial on installing Python3 in MacOS Big Sur

> ## IMPORTANT!!!
> - Python3 comes with MacOS Big Sur 
> - BUT better to install again with Homebrew
> - Homebrew-Python3 also installs pip, setuptools, and wheel (very important!)

## STEP-BY-STEP INSTALLATION
- [1] Install **Xcode** (along with **Command Line Tools** and **Git**)
  - Check if Xcode is already installed -> in Terminal, `- xcode-select -p`
    - If directory exists, Xcode is installed   
    - If not, install Xcode from App Store
  - Git is installed with Xcode -> check if Git is installed : `git --version`
  - **Xcode Command Line Tools** will be installed in step [2]

- [2] Install **Homebrew** (& **Command Line Tools**)
  - Homebrew is a package manager that let's you install stuff that Apple or Linux didn't need
  - Homebrew is made with Ruby, so it will be modifying your computer’s Ruby path. 
  - Open Terminal, and paste :
  - ```/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"```
    - The curl command pulls a script from the specified URL. 
    - This script will explain what it will do and then pauses the process to prompt you to confirm. This provides you with a lot of feedback on what the script is going to be doing to your system and gives you the opportunity to verify the process.  
  - Confirm Homebrew installation -> `brew doctor`
  - This will also install **Xcode Command Line Tools** (this step takes a while... many GB)
    - Confirm installation by `xcode-select -p` -> Directory will show up (.../CommandLineTools)

- [3] Install **Python3**
  - In Terminal -> ```brew install python3```
  - Along with Python 3, Homebrew will install **pip3**, **setuptools**, and **wheel**
    - (TO UPGRADE : `brew upgrade`, e.g. `brew upgrade python3`)
  - Place Homebrew directory at the top of the PATH environment variable
    - This will ensure that Homebrew installations will be called over the tools that Mac OS X may select automatically that could run counter to the development environment we’re creating.
    - You should create or open the ~/.bash_profile file -> `vi ~/.bash_profile`
    - Add the following -> `export PATH=/usr/local/bin:$PATH`
    - Source to activate changes -> `source ~/.bash_profile`

- [4] (OPTIONAL) Install VSCode & extensions
  - Install `Python extension for Visual Studio Code`
  - Select Python Interpreter
    - Open Command Palette (⇧⌘P) -> search for "Python: Select Interpreter"
    - Select `Python 3.9.5 64-bit, /usr/local/bin/python3` 
    - IMPORTANT! Ensure that interpreter Path is the same is as we defined in `.bash_profile (/usr/local/bin)
  - Install packages by :
    - `pip3 install package-name`

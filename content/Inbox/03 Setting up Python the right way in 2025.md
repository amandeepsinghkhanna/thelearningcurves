---
title: Setting up Python the right way in 2025
author: Amandeep Singh Khanna
tags:
  - datascience
  - python-programming
  - set-up
  - dev-environment
  - ai
  - ml
---
Ever since Anaconda pulled a fast one on us by making Python usage for commercial and academic purposes a paid affair, I've been searching for a Python package management solution that isn't controlled by a large corporate entity. I went through a lot of options to find the one that finally felt perfect and as seamless as Anaconda. 
# 1. Installing pyenv
Pyenv can be installed on a windows system by running the following command on the PowerShell.
```bash
Invoke-WebRequest -UseBasicParsing -Uri "https://raw.githubusercontent.com/pyenv-win/pyenv-win/master/pyenv-win/install-pyenv-win.ps1" -OutFile "./install-pyenv-win.ps1"; &"./install-pyenv-win.ps1"
```
In case you run into an error that PowerShell is not authorized for running scripts, try running the script below on PowerShell and then the command specified above.
```bash
Set-ExecutionPolicy RemoteSigned
```
To be able to use pyenv, close and re-start PowerShell.
# 2. Installing different versions of Python
Pyenv like Anaconda package manager helps us install multiple versions of python. 
## 2.1. Getting list of python versions available for installation
```powershell
pyenv install --list
```
## 2.2. Installing a specific version of Python
```powershell
pyenv install <name of the python version from the list>
```
## 2.3. List all the installed versions of Python
```powershell
pyenv versions
```
## 2.4 Setting a default version of Python
```powershell
pyenv global <name of the python version from the list>
```
Setting a version of Python as a global version makes it the default version that is chosen to execute your code unless explicitly specified.
## 2.5 Checking if setting the default version of Python worked
```powershell
python --version
```
This command should show the version of Python set as the default/global version in the previous command.
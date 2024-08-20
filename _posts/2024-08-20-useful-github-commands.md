---
layout: post
title: a post with code
date: 2024-08-20 15:09:00
description: usefull github commands
tags: formatting code
categories: code
featured: false
---

## Jupyter Kernel spec
Register environment as a jupyter kernel

> mamba install jupyterlab ipykernel

> python -m ipykernel install --user --name=env_name

Remove jupyter kernel
> jupyter kernelspec remove env_name


## Pip env
To create a pip env navigate to project directory

> py -m venv env

activate
> .\my_env_name\Scripts\activate

install standard packages using basic_requirments.txt
> pip install -r /path/to/requirements.txt

## Git
### Initialise Git remote from local repo
Make it a Git repo, creating main branch
> git init -b main

Add and commit files
> git add .

> git commit -m"initial commit"

### Create remote on Github.com
Create new project with **same name** as local repo on GitHub.com
Create **without** *README.md* and *.gitignore* files

### Link local to remote 
Add remote origin
> git remote add origin https://github.com/USER/PROJECT.git

Verify with 
> git remote -v

Push files
> git push origin main
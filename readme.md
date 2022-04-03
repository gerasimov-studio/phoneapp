# How to create Django web application using Android?

The purpose of this example is to show that you can create a complete web application using just your Android mobile phone or tablet. The following few simple steps will show you how to start developing on your phone. Also you will find information about tools you need.

## Tools

First of all you need to install [Termux](https://termux.com/) app. It is the linux environment and terminal emulator. For installation use F-Droid, because the version placed on Play Market is deprecated. After installation update Termux.

Then you need a code editor. I use [Code Ediotor from Rhythm Software](https://play.google.com/store/apps/details?id=com.rhmsoft.code), but you can use any editor you prefer.

## Get Started

Launch Termux and update packages:
```
pkg update && pkg upgrade
```

Setup Termix storage:
```
termux-setup-storage
```
Then allow Termux to access file system of your device

Install Python:
```
pkg install python
```

Install Git:
```
pkg install git
```

Install GitHub CLI if you want to easily create repository and publish your project on GitHub
```
pkg install gh
```

## Create your project

Create a folder for your project. For example my projects are in ~/Projects dir. Create Projects dir:
```
cd ~
mkdir Projects && cd Projects
```

Then create a directory for your project. For example:
```
mkdir MyApp && cd MyApp
```

Setup virtual environment in your project directory with command python -m venv < name >. For example:
```
python -m venv venv
```
  
Activate your virtual environment with command source < venv >/bin/activate where < venv > is name from previous step (venv in this example):
```
source venv/bin/activate
```

Now you are ready to install Django in your activated virtual environment. Use pip package installer for it:
```
pip install django
```
  
Save required packages to requrements.txt:
```
pip freeze > requirements.txt
```
  
Start a new Django project with your project name: django-admin startproject < project name >
```
django-admin startproject MyApp
```
  
Run local server to have a look at your project:
```
cd MyApp
python manage.py runserver
```
If everything is ok, open your browser and navigate to 127.0.0.1:8000. You will see a welcome page of your new Django project. Hooray!
To stop the project use Ctrl+C combination.

## Initialize Git and create GitHub repository
  
Then initialize your local project directory as a Git repository:
```
git init -b main
```
  
Create .gitignore file to ignore caches, logs etc.
```
nano .gitignore
```
Put to .gitignore file following rows:
```
*.log
*.pot
*.pyc
__pycache__/

.env
```
  
Add files of your project to Git and commit
```
git add . && git commit -m "Initial commit"
```
  
Then if you want publish your project on GitHub create a GitHub repository using GitHub CLI. First of all you should authenticate:
```
gh auth login
```
Answer the questions and login GitHub with a web browser
  
Then create a repository:
```
gh repo create  
```
Choose "Push an existing local repository to GitHub" option
  
Congratulations! Your project is ready to be developed!

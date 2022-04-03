# How to create Django web application using Android?

The purpose of this example is to show that you can create a complete web application using just your Android mobile phone or tablet. The following few simple steps will show you how to start developing on your phone and what tools you need to do it.

## Tools

First of all you need to install [Termux](https://termux.com/) app. It is linux environment and terminal emulator. For installation use F-Droid, because version placed in Play Market is deprecated. After installation update Termux.

Then you need some code editor. I'm using [Code Ediotor from Rhythm Software](https://play.google.com/store/apps/details?id=com.rhmsoft.code), but you can use another one what you want.

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

Install GitHub CLI if you want to easily create repository and publish your project in GitHub
```
pkg install gh
```

## Create your project

Create folder for you project. For example my projects are in ~/Projects dir. Create Projects dir:
```
cd ~
mkdir Projects && cd Projects
```

Then create directory for your project. For example:
```
mkdir MyApp && cd MyApp
```

Setup virtual environment in yor project directory with command python -m venv < name >. For example:
```
python -m venv venv
```
  
Activate you virtual environment with command source < venv >/bin/activate where < venv > is name from previous step (venv in this example):
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
  
Run local server and watch your project:
```
cd MyApp
python manage.py runserver
```
If everything is ok, open your browser and navigate to 127.0.0.1:8000. Your will see welcome page of your new Django project!
  
## Initialize Git and create GitHub repository
  
If your project are runing, stop it by Ctrl+C combination.
Then initialize your local project directory as Git repository:
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
  
Then if you want publish you project in GitHub create repository on GitHub using GitHub CLI. First authenticate:
```
gh auth login
```
Answer the questions and login GitHub with a web browser
  
Then create repository:
```
gh repo create  
```
Chouse "Push an existing local repository to GitHub" variant
  
Congratulations! Your project is ready to be developed!

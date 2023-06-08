# DASH-WEBSITE
DASH-WEBSITE

How to deploy:

* Deploy Flask Dash App to Heroku in Python
* Sign up for account on Heroku
* Create your App name (this will be part of the url)
* Download and install Heroku CLI (allow you to create and manage your Heroku apps directly from the terminal)
* Create new project in Pycharm (where your app code and files will be located)
* Choose new environment using Virtualenv
* Select a python Base interpreter (no need to check the boxes under interpreter
* Create a new .py file to start writing the code for your app.If you already created the code for your app, copy those files into your new project folder.
* Inside your app’s file, under “app = dash.Dash(__name__)”, add this line: server = app.server
* Open terminal, and cd into your project folder if necessary
* Pip install any libraries and specific versions your app needs. My app uses the following (install any version you want):

  * pip install numpy==1.18.1
  * pip install pandas==1.0.0
  * pip install plotly==4.8.0
  * pip install dash==1.12.0
  * pip install gunicorn==20.0.4(needed to run app on heroku)
* Create .gitignore file inside your project folder (tells Git which files or folders to ignore in a project) and add these lines into it:

  * venv *.pyc .env .DS_Store (4 separate lines)
* Create a Procfile inside same folder and add this line inside:

  * web: gunicorn YourAppFileWithout.py:server
* Create requirements. Go back to terminal, cd to project folder if necessary, and type:

  * pip freeze > requirements.txt
* Inside terminal, type the following-

  * heroku login
  * -git init
  * heroku git:remote -a  AppNameFromStep2
  * git add .
  * git commit -am "initial launch"
  * git push heroku master

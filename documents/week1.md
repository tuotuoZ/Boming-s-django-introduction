#Week 1 report
This week I have followed the [official django tutorial](https://docs.djangoproject.com/en/3.0/intro/tutorial01/) from part
1 to part 3. In part 2,I realized that some database knowledge is essitial for better understanding the web development. Learning database concept
is in my next week to do list.

### Part 1: Initialize the project
#### Command cheatsheet
 Here is a list of useful command lines:
```shell script
#To initialize the project
django-admin startproject mysite

#To start the server
#You can specify the server port at the end of the command e.g. 8080
python manage.py runserver

#Create a application named polls inside the project
python manage.py startapp polls


```
####Summary
1. Create the project
2. Create the app inside the project
3. Create the view of your app
4. Map the view to a url. This can be done by modifying the url files in project and app directory.

### Part 2: Setup the database, Create models, Intro to admin site
#### Command cheatsheet
```shell script
#Check the included apps from INSTALLED_APPS list, and create data table in the database.
python manage.py migrate

#Tell Django there is a change in the polls, and store them as migration.
python manage.py makemigrations polls

#SQL migration which takes migration names and returns their SQL.
python manage.py sqlmigrate polls 0001

#this checks for any problems in your project without making migrations or touching the database.
 python manage.py check

#It sets the DJANGO_SETTINGS_MODULE environment variable, 
# which gives Django the Python import path to your mysite/settings.py file.
python manage.py shell

#Create superuser for the admin site
python manage.py createsuperuser


```

####Summary
1. Confirm your database in project/setting.py file
2. Set TIME_ZONE to match your time zone. e.g. 'US/Eastern'
3. Allocate the space in the db for apps usign migrate command.
4. Create models in app/models.py
5. Include the app in app/settings.py under INSTALLED_APPS list.
6. Create migration for changes and apply them using migrate.
7. Modify the data in db using python shell for SQLlite
8. Go to “/admin/” on your local domain after you create the super user.
9. Make your app modifiable in the admin by register the model in app/admin.py
9. Change app data through admin site.

###Part 3: Write views and raise a 404 error
#### Command cheatsheet
```shell script

```
####Summary
1. Django has a more elegant way to handle URL patterns, using / to differenciate apps.(Compared to “ME2/Sites/dirmod.asp?sid=&type=gen&mod=Core+Pages&gid=A6CD4967199A42D9B65B1B”)
2. Add more views in app/views.py
3. Route those views in app/urls.py
4. Create templates folders inside app folder and create a template .html
5. Load the html file template from views.py
6. We can also use the render function as  a shortcut for template loader
7. Use this in views.py to raise a 404 error
```python
get_object_or_404()
```
8 . Removing hardcoded URLs in templates by using {% url %}. It will match the name you assign in the path function
under the urls.py.
9 . Give a namespace to your app's urls.py, so django knows how to differentiate the name in URL between different 
apps.

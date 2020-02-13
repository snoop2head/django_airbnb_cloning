# Airbnb Clone

- Cloning Airbnb tutorial with Django, Tailwind
- Purpose is to make website for fitcuration: exercise recommendation system

# 2. Creating a Django Project
```shell
pipenv shell
django-admin startproject config
```
- Change the config directory of the project
- Drag (inside) config directory and manage.py file out of the original config directory
- You can change python settings on the low deck of VSCode
- Recommending flake 8 as linter. it is automatically recommended through vscode 
- Recommending black as formatter

```shell
 pipenv install black --dev --pre
```

- Selecting linter and formatter for the project is recorded on .vscode/settings.json file
- __init___.py is helps to work like python package
- Inside of settings.py, look at django documentation links
- In Django documentation you can even look at code, like https://docs.djangoproject.com/en/2.2/_modules/django/contrib/auth/password_validation/#CommonPasswordValidator
- On VSCode Windows, CMD + Mouse Click on function to see the source code 
- Run your server, Where pipenv is activated (= inside the bubble).

```shell
python manage.py runserver
```

- You'll have localhost connection.
- You can also access to admin panel page, which is  http://127.0.0.1:8000/admin/login/?next=/admin/
- without manage.py, database table doesn't exist. Thus this kind of error appears on console log. 
**You have 17 unapplied migration(s). Your project may not work properly until you apply the migrations for app(s): admin, auth, contenttypes, sessions. Run 'python manage.py migrate' to apply them.**
- SQL needs to learn how database look like. 
- You change the shape of data(=creating migration), and migrate to update database
- Updating Database: Django shapes the data(or change the shape), you create migration, you apply migration
- Therefore, configurate SQL(Structured Queried Language) database with 

```shell
python manage.py migrate
```

- Django project is group of applications (= just say Django is a group of functions).

**Projects vs. apps**

What’s the difference between a project and an app? An app is a Web application that does something – e.g., a Weblog system, a database of public records or a small poll app. A project is a collection of configuration and apps for a particular website. A project can contain multiple apps. An app can be in multiple projects.
Source: https://docs.djangoproject.com/en/3.0/intro/tutorial01/

- We should not have so much functionality in one folder(=application)
- If it is folder of list, it should be simple as such: Create list, Read List, Update List and delete list 
- Applications should be separate. 
- Django project is made of many small applications. when to create application / when not to create application is important

**You should be able to describe an application in one sentence.** If you use the word "and", then it should be diferent application. **Divide and conquer**

```shell
 django-admin startapp [appname]
```
- since app contains multiple functions, appname should be in plural form
- names of .py files in application folder is not optional. You can't change names
- for example, users app has create password, update password

### configuration directory structure
- settings.py: you can refer to installed default apps in django.
- __init___.py:  helps to work like python package
- urls.py: controls url of the website. Can also be established under application. 

### application directory structure

- admin.py: reflects changes on admin panel
- apps.py: just configuration file
- models.py: describing how database look like
- views.py: function that renders html
- urls.py: you can create urls.py under an application.
like /users/profile, /users/delete, /users/register etc.

## 3. Building Users Applications

- replacing django user with my user
- Python is object programming language: class can be inherited!
- CMD + click to check Abstractuser class
- Django makes migration by itself, so we don't have to write sql

```shell
python manage.py makemigrations
python manage.py migrate
```

- Django has database fields for everything: email field, text field... Just call for fields. 

![image-20200213015216499](/Users/noopy/Library/Application Support/typora-user-images/image-20200213015216499.png)

- installing module on python virtual environment SHOULD NOT BE DONE WITH pip. 
  Use pipenv

  ``` shell
  pipenv install Pillow
  ```

  

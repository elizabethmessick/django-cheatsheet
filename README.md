# django-cheatsheet

## How to create a new Django project 
```bash
django-admin startproject projectname 
``` 

## How to start the Django development server
```bash
python3 manage.py runserver
```
## But how do I stop it? 
```bash
ctrl + C
```

## How to create a new application in the project 
```bash
python3 manage.py startapp main_app
```

## Django Directory Structure
```
djangoproject
|
|- djangoproject
|  |- settings.py: Main settings for projects (db, apps, config, etc.)
|  |- urls.py: Main URLS for entire project 
|
|- application_name
|  |- static: (dir) This holds all static files (css, js, images, aux, forms)
|  |- templates: (dir) This holds all HTML template files 
|  |- migrations: (dir) This holds all data migration files
|  |- admin.py: this is where we register data models 
|  |- models.py: This is where we put all data models
|  |- views.py: This is where we put the functions that run our routes 
|  |- urls.py: Every URL for our site is defined here 
|
|- manage.py: Let's us manage everything about our project 
```

## How to make URLs with the path() function 
```python
urlpatterns = [
  path('route1/', views.route1_name, name='route1_name'),
  path('route2/<string_variable>', views.route2_name, name='route2_name'),
  path('route3/<int:variable_name>', views.route3_name, name='route3_name'),
]
```
#### The first parameter is the actual location, the url. The full thing should be in quotes.  
#### The second parameter is the name of the function
#### The third parameter is the nname you give to the path 

## How to make a view function
```python
def route1_name(request):
  return render(request, 'template1.html')

def route2_name(request, string_variable):
  return render(request, 'template2.html', {'data': string_variable})
    
def route3_name(request, variable_name):
  return render(request, 'template3.html', {data: variable_name})
```

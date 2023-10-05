# Polls API

Here is the link to the documentation for this djangorestframework project.
- https://books.agiliq.com/projects/django-api-polls-tutorial/en/latest/

I will be correcting any bugs as I go building the project/ documentation as it is written in the link.


### Create main directory
The official documentation does not include the fact you must create the directory yourself.

You MUST create the directory before you create the virtual environment, otherwise you will simply create the virtual environment whereever your terminal is.

###### Create main directory
Navigate to wherever you want to create your project directory.

Create your main directory with the following command

```
mkdir drf_poll_example_api
```

### Create virtual environment

#### Your tree before you create the virtual environment
```
tree -L 3  
```
```
.
└── README.md

1 directory, 1 file
```

Now run the following command to create the virtual environment
```
python3 -m venv env
```

#### Your tree after you create the virtual environment
```
.
├── README.md
└── env
    ├── bin
    │   ├── Activate.ps1
    │   ├── activate
    │   ├── activate.csh
    │   ├── activate.fish
    │   ├── pip
    │   ├── pip3
    │   ├── pip3.10
    │   ├── pip3.11
    │   ├── python -> python3.11
    │   ├── python3 -> python3.11
    │   └── python3.11 -> /Library/Frameworks/Python.framework/Versions/3.11/bin/python3.11
    ├── include
    │   └── python3.11
    ├── lib
    │   └── python3.11
    └── pyvenv.cfg

7 directories, 13 files
```

We should see a folder named env with a bin directory which include the activate file which we will need to run so the virtual environment is activated.

Run your virtual environment with the following command
```
source env/bin/activate
```

Now that your virtual environment is activated we should see your terminal prompt be prefixed with the name of the virtual environment in parentheses. 

It should look like this:
```
(env) ~/Desktop/drf_poll_example_api  (main) $ 
```

#### NOTE: DO NOT USE mkvirtualenv
There are a lot of configs to make this approach work properly which isn't worth your time. It makes creating the virtual environment more difficult so use this way instead.

Disregard mkvirtualenv when creating the virtual environment for this project and moving forward as well.

### Install Django

Again, make sure you're in your virtual environment before installing dependencies or the process will fail.

```
pip3 install Django
```
This will install Django and subdependencies to your virtual environment

```
asgiref==3.7.2
Django==4.2.6
sqlparse==0.4.4
```
```
pip3 install djangorestframework
```
This will install djangorestframework and subdependencies to your virtual environment

```
djangorestframework==3.14.0
pytz==2023.3.post1
```

Don't forget to run your 

```
pip3 freeze > requirements.txt
```
Overall your requirements.txt should look like the following once both are installed.
```
asgiref==3.7.2
Django==4.2.6
djangorestframework==3.14.0
pytz==2023.3.post1
sqlparse==0.4.4
```

### Start django-admin project

#### Make sure to check your tree
```
tree -L 3  
```
Correct command:
```
django-admin startproject pollsapi .
```
Correct Tree:
```
.
├── README.md
├── env
│   ├── bin
│   │   ├── Activate.ps1
│   │   ├── activate
│   │   ├── activate.csh
│   │   ├── activate.fish
│   │   ├── django-admin
│   │   ├── pip
│   │   ├── pip3
│   │   ├── pip3.10
│   │   ├── pip3.11
│   │   ├── python -> python3.11
│   │   ├── python3 -> python3.11
│   │   ├── python3.11 -> /Library/Frameworks/Python.framework/Versions/3.11/bin/python3.11
│   │   └── sqlformat
│   ├── include
│   │   └── python3.11
│   ├── lib
│   │   └── python3.11
│   └── pyvenv.cfg
├── manage.py
├── pollsapi
│   ├── __init__.py
│   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
└── requirements.txt

8 directories, 22 files
```

#### NOTE: The actual documentation unfortunately forgets to tell you to include the ' . ' at the end of the command, don't make this mistake or your tree will look like this! You only want one polls_api director, not two nested like this!
Inorrect command:
```
django-admin startproject pollsapi 
```
Incorrect Tree:
```
.
├── README.md
├── env
│   ├── bin
│   │   ├── Activate.ps1
│   │   ├── activate
│   │   ├── activate.csh
│   │   ├── activate.fish
│   │   ├── django-admin
│   │   ├── pip
│   │   ├── pip3
│   │   ├── pip3.10
│   │   ├── pip3.11
│   │   ├── python -> python3.11
│   │   ├── python3 -> python3.11
│   │   ├── python3.11 -> /Library/Frameworks/Python.framework/Versions/3.11/bin/python3.11
│   │   └── sqlformat
│   ├── include
│   │   └── python3.11
│   ├── lib
│   │   └── python3.11
│   └── pyvenv.cfg
├── pollsapi
│   ├── manage.py
│   └── pollsapi
│       ├── __init__.py
│       ├── asgi.py
│       ├── settings.py
│       ├── urls.py
│       └── wsgi.py
└── requirements.txt

9 directories, 22 files
```

### Database setup

By default your database is set up in your pollsapi/settings.py file.

It should look like this:

```
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': BASE_DIR / 'db.sqlite3',
    }
}
```
If you notices the name of your database it points to the sqlite3 database/ file in your base directory.

The file will be generated when we run the migrate command.

```
python3 manage.py migrate
```

You should now see a db.sqlite3 file at the root of your base directory. 

This file cannot be read by vscode but we can access it like any other database by simply running our app once we have everything set up with the following command ( make sure you are in the directory that includes your manage.py file ):

```
Python3 manage.py runserver
```
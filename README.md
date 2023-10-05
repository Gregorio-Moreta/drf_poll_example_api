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








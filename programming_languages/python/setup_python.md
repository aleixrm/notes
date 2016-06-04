---
Setting up python
---


* Download essential packages with pip (check that python Scripts directory is in the PATH, in order to find pip)
** Setuptools https://pypi.python.org/pypi/setuptools
** Virtualenv sets virtual environments for different library versions of python
```
pip install virtualenv
```

* creating virtual environments with virtualenv (Follow the guide in https://docs.djangoproject.com/en/1.9/intro/contributing/)
```
#Create the folder that will contain the virtual env
mkdir .virtualenv
#Call virtualenv with the virtual environment name
virtualenv <virtualenv_name>
#(Maybe you have to set the ExecutionPolicy to remote signed in power shell before in order to source the script)
Set-ExecutionPolicy RemoteSigned
#Activate the virtualenv with source
. .virtualenvs/<virtualenv_name>/Scripts/activate
#You have to activate the virtualenv whenever you open a new terminal window. #virtualenvwrapper is a useful tool for making this more convenient.
```

####Python Style Guide (a.k.a. PEP 8)
https://www.python.org/dev/peps/pep-0008/

####Python programming FAQ
https://docs.python.org/2.7/faq/programming.html

#####Library reference
https://docs.python.org/2.7/library/index.html

#####Language reference
https://docs.python.org/2.7/reference/index.html

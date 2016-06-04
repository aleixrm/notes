---
Django setup
---
####Set up django in virtualenv
```
#Create the django virtualenv
mkdir .virtualenvs/djangoenv
#(Maybe you have to set the ExecutionPolicy to remote signed in power shell before in order to source the script)
Set-ExecutionPolicy RemoteSigned
#Activate the virtualenv with source
. .virtualenvs/<virtualenv_name>/Scripts/activate
#Once the virtualenv for django is created, we can install django with pip
pip install django
#Verify django installation (It should return django version without error)
python -c "import django; print(django.get_version())"
```



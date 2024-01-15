
Be **Extremely** careful when trying to change the default python version on Ubuntu linux.  It relies on Python more than I would have thought!  It's best practice to make virtual environment for your projects anyways. 

## Making a new virtual env

```
python3 -m venv name_of_env
```

The above command creates a directory named 'my_env_project' in the current directory, which contains pip, interpreter, scripts, and libraries.

then run the following: 

```
source name_of_env/bin/activate
```

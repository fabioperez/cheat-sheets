# virtualenv

### Install

```Bash
pip install virtualenv
```


### Basic Usage

```Bash
cd my_project_folder

# Default
virtualenv venv

# Custom Python interpreter
virtualenv -p /usr/bin/python2.7 venv

# Don't include the packages that are installed globally
virtualenv --no-site-packages venv

# Activate
source venv/bin/activate

# Deactivate
deactivate
```


### Requirements

```Bash
# Freeze the current state of the environment packages
pip freeze > requirements.txt

# Install requirements
pip install -r requirements.txt
```


## Tools

### [virtualenvwrapper](https://virtualenvwrapper.readthedocs.io/)

#### Install

1. Run `sudo pip3 install virtualenvwrapper`

2. Add to shell file:

```
export VIRTUALENVWRAPPER_PYTHON='/usr/bin/python3'
export VIRTUALENVWRAPPER_VIRTUALENV='/usr/bin/pyvenv'
export WORKON_HOME=$HOME/.virtualenvs
source /usr/local/bin/virtualenvwrapper.sh
```

#### Usage

Create virtual environment:

`mkvirtualenv project_name`

Work on virtual environment:

`workon project_name`

Deactivate:

`deactivate`

Delete:

`rmvirtualenv project_name`

### [autoenv](https://github.com/kennethreitz/autoenv)

If a directory contains a `.env` file, it will automatically be executed when you `cd` into it.

#### Install
```Bash
# macOS
brew install autoenv
echo "source $(brew --prefix autoenv)/activate.sh" >> ~/.bash_profile

# Ubuntu
pip install autoenv
echo "source `which activate.sh`" >> ~/.bashrc
```

## To Do
* Integration with ZSH


## References

Virtual Environments - The Hitchhiker's Guide to Python - http://docs.python-guide.org/en/latest/dev/virtualenvs/

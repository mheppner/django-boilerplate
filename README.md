# Django Boilerplate

- Tested with Python 3 only
- Environment variables (or `.env` file) for configuration
- Basic health check endpoint
- Configs for flake8, pydocstyle, and editorconfig
- Circus deployment for managing processes
- Complete separation of runtime files (static/media files, logs, file-based cache, etc.)

## Requirements

- Python 3.5+


## Installation

```sh
# create a virtual environment
python3.6 -m venv env
source env/bin/activate

# install requirements
pip install -r requirements/common.txt
# pip install -r requirements/dev.txt
# pip install -r requirements/prod.txt

# edit your local environment settings
cp .env.sample .env
vi .env

# apply migrations
cd src
./manage.py migrate
```

## Deployment

```sh
# enter the virtual environment
source env/bin/activate

# make sure migrations are applied and gather static files
cd src
./manage.py migrate
./manage.py collectstatic --noinput

# start circus in the background
circusd --daemon circus.ini

# view process state
circusctl

# kill everything
kill `cat data/run/circusd.pid`
```

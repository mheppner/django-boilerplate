# Project

*[Description]*

## Requirements

- Python 3.5+


## Installation

```sh
python3.6 -m venv env
source env/bin/activate

pip install -r requirements/common.txt
# pip install -r requirements/dev.txt
# pip install -r requirements/prod.txt

cd src
./manage.py migrate
```

## Deployment

```sh
source env/bin/activate

circusd circus.ini
```

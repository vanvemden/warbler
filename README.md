# warbler

A Twitter clone using Python, Flask, Bcrypt, SQLAlchemy, WTForms, Jinja.

## Setup

Create the Python virtual environment:

```
$ python3 -m venv venv
$ source venv/bin/activate
(venv) $ pip install -r requirements.txt
```

Set up the database:

```
(venv) $ createdb warbler
(venv) $ python seed.py
```

Start the server:

```
(venv) $ flask run
```

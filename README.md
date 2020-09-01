![Warbler logo](https://github.com/vanvemden/warbler/blob/master/static/images/warbler-logo.png)

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

## Running Tests

To run a file containing unittests, run the command:

```
FLASK_ENV=production python -m unittest <name-of-python-file>
```

## Routes

| Route                            | Methods   | Template             | Template arguments | Description           |
| -------------------------------- | --------- | -------------------- | ------------------ | --------------------- |
| /                                |           | home.html            | messages, likes    | Home page             |
| /signup                          | GET, POST | users/signup.html    | UserAddForm        | Handle user signup    |
| /login                           | GET, POST | users/login.html     | LoginForm          | Handle user login     |
| /logout                          | GET       | N/A                  | N/A                | Handle user logout    |
| /users                           | GET       | users/index.html     | users              | List users            |
| /users/:user_id                  | GET       | users/show.html      | user, messages     | Show user profile     |
| /users/:user_id/following        | GET       | users/following.html | user               | List who user follows |
| /users/:user_id/followers        | GET       | users/followers.html | user               | List who follows user |
| /users/follow/:follow_id         | POST      | N/A                  | N/A                | Follow user           |
| /users/stop-following/:follow_id | POST      | N/A                  | N/A                | Unfollow user         |
| /users/profile/password          | GET, POST | users/password.html  | UserPasswordForm   | Change password       |
| /users/profile                   | GET, POST | users/edit.html      | UserEditForm       | Edit user profile     |
| /users/delete                    | POST      | N/A                  | N/A                | Delete user           |
| /messages/new                    | POST      | N/A                  | N/A                | Add message           |
| /messages/:message_id            | GET       | messages/show.html   | message            | Show message          |
| /messages/:message_id/like       | GET,POST  | N/A                  | N/A                | Like/unlike message   |
| /users/:id/likes                 | GET       | likes.html           | messages, user     | List user likes       |
| /messages/:message_id/delete     | POST      | N/A                  | N/A                | Delete message        |

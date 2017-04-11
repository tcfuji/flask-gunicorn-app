## Flask Gunicorn App for foodRev-Planner

### Setup Instructions

1. Install the necessary Ubuntu Repositories:
```
$ sudo apt-get update
$ sudo apt-get install python-pip python-dev nginx
```

2. Create a Python Virtual Environment
```
$ sudo pip install virtualenv
```

3. Clone the `flask-gunicorn-app` repository.
```
$ git clone
```

4. Create a virtual environment that stores the Flask project's Python requirements and activate the virtual environment.
```
$ virtualenv flaskenv
$ source flaskenv/bin/activate
```

5. Install Gunicorn and Flask.
```
(flaskenv) $ pip install gunicorn flask
```

6. Allow access to port 5000.
```
(flaskenv) $ sudo ufw allow 5000
```

7. Test Flask app.
```
(flaskenv) $ python myproject.py
```

8. Visit http://localhost:5000

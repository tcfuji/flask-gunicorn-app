## Flask Gunicorn App for foodRev-Planner

(Shortened version of https://www.digitalocean.com/community/tutorials/how-to-serve-flask-applications-with-gunicorn-and-nginx-on-ubuntu-16-04)

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
6. Deactivate the virtual environment.
```
(flaskenv) $ deactivate
```

7. Move `myproject.service` to the `/etc/systemd/system` directory.
```
$ mv myproject.service /etc/systemd/system
```

8. Start the Gunicorn service and enable it so that it starts at boot.
```
$ sudo systemctl start myproject
$ sudo systemctl enable myproject
```

9. Move `myproject` file to `/etc/nginx/sites-available` directory.
```
$ mv myproject /etc/nginx/sites-available
```

10. To enable the Nginx server block configuration we've just created, link the file to the sites-enabled directory.
```
$ sudo ln -s /etc/nginx/sites-available/myproject /etc/nginx/sites-enabled
```

11. Restart the Nginx process to read the our new config.
```
$ sudo systemctl restart nginx
```

12. Allow access to the Nginx server.
```
$ sudo ufw allow 'Nginx Full'
```

13. Enter `http://localhost` in your web browser.

## OG Deployment

```
# test the server locally
pip install -r requirements.txt
gunicorn app:app

# login to heroku
heroku login

# create an app
heroku create myapp-name-1

# set a git alias for heroku
git remote add heroku https://git.heroku.com/myapp-name-1.git

# commit everything
git add .
git commit -m 'initial commit'

# deploy
git push heroku master

# view the app
heroku open
```

## Docker Deployment

```
# log in to heroku cli
heroku login
heroku container:login

# create the app
heroku create myapp-name-2

# create the container with format:
# docker build -t registry.heroku.com/<app name>/<process type> .
docker build -t registry.heroku.com/myapp-name-2/web .

# push the image to the registry
docker push registry.heroku.com/myapp-name-2/web

# "release" the image
heroku container:release --app myapp-name-2 web

# open the app
heroku open --app myapp-name-2
```
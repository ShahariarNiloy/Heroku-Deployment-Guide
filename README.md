# Heroku-Deployment-Guide

## Heroku Configuration

1) Create a Heroku account.
2) Download Heroku CLI from [here](https://devcenter.heroku.com/articles/heroku-cli#download-and-install).

# Backend / Server Deploy

1) Create a Heroku app.
2) Change your Node app port to
```
process.env.PORT || <any port number>
```


3) Set your environment variables on Heroku. 
```bash
<your heroku app dashboard>
    |-- Settings
        |-- Config Vars
            |-- KEY: <your env variable names>
            |-- VALUE: <your env variable value>
```

These variables will work as your `.env` file. In your project, where env variables are set, will look forward in these heroku variables. If found, then will work fine but if not then you may see `Application Error`. 

4) After above heroku configuration Run these codes.
```bash
heroku login
```
```bash
git init
```
```bash
heroku git:remote -a <app-name>
```
```bash
git add .
```
```bash
git commit -am "my first commit"
```
```bash
git push heroku master
```

5) Go to your heroku app dashboard and click `Open App`. Voila, your app is running good.


# Frontend / Client Deploy

1) Create your app
2) Change your all API_URL from `localhost` to deployed API_URL

Example.
From
```bash
fetch('localhost:5000/api/users')...
```
To
```bash
fetch('workout-hub-backend.herokuapp.com/api/users')...
```
3) Then run these code
```bash
heroku login
```
```bash
git init
```
```bash
heroku git:remote -a <app-name>
```
```bash
heroku create -b https://github.com/mars/create-react-app-buildpack.git
```
```bash
git add .
```
```bash
git commit -am "my first commit"
```
```bash
git push heroku master
```

4) Go to your heroku app dashboard and click `Open App`. Voila, your app is running good.

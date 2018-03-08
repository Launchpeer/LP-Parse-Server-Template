_The purpose of this document is to provide instructions for how to spin up a fresh Parse database server that can then be used by a Launchpeer web or mobile app_

**IMPORTANT!**
Log in to Heroku using the hello@launchpeer.com credentials

this is important, because we will need to use the credit card on file

_NOTE: after you deploy the server, please log out and use your own heroku user credentials to keep track of your activity_

## STEP 1: Github

Click [![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy) (you'll be taken to Heroku.com).


_NOTE: Installation Instructions in this repo's README only apply if you need to deploy from a organization other than Launchpeer_


## STEP 2: Heroku

Set app name: 
`someproject-backend`
example : `mylai-backend`

Create new pipeline
under Choose a stage to add this app to choose `staging`

Initial Config Variable to set up:
`PARSE_APP_ID` - match to your app name
`PARSE_SERVER_ID` - set your app name here before `.herokuapp.com/parse`
_example : https://mylai-backend.herokuapp.com/parse_
`PARSE_DASHBOARD_APP_NAME`
_example: mylai_

All other config variables can be set later

Click `Deploy app`

Once you get feedback that your server has deployed to Heroku, you can Manage App or View

Pat yourself on the back! You have officially deployed a fresh Parse Database Server!

## STEP 3: Viewing Dashboard

Your dashboard can now be found at your `PARSE_SERVER_ID` + /dashboard
_example https://mylai-backend.herokuapp.com/dashboard_

You can log in with the credentials you set in your Config Vars
you want to use the values for the keys `PARSE_ADMIN_DASHBOARD_USERNAME` and `PARSE_ADMIN_DASHBOARD_PASSWORD`
you can always find / edit these variables by going to your Heroku app dashboard > Settings > Config Variables
_example : https://dashboard.heroku.com/apps/mylai-backend/settings_

You will see an app matching `PARSE_DASHBOARD_APP_NAME` listed on this screen. Click it to enter your DB

### About What you'll see in the dashboard
You are currently looking at a fresh database with two classes that Parse provides out of the box - `Role` and `User`

## STEP 4: Bringing it all together

### Github

**clone the Launchpeer Parse server repo**

`git clone https://github.com/Launchpeer/lp-parse-server-template`

**rename the directory:**

example: `mv lp-parse-server-template mylai-backend`

**clear the README** (since it pertains to launching the server)

_NOTE: use the following command with the name of your folder_

`cd mylai-backend && > README.md`

**exit with**

`ctrl-c`

**add your changes and commit**

`git add .
git commit -m 'new server initial commit`

**remove the origin**

`git remote rm origin`

**Create a new empty repo in Github**

**add your new origin**

_NOTE: Use your own repo name in the following command_

`git remote add origin https://github.com/Launchpeer/my-new-repo.git
git push -u origin master
`
### Heroku

Go to the Heroku instance you spun up.

Under `Deploy` click `Github` as the `Deployment Method` and connect to the Github repo you just created

# FSND_Capstone
# Live Application URL
Access the application using the following URL:
https://myfsnd-app-ccf72007e807.herokuapp.com/
# Casting Agency Specifications
The Casting Agency models a company that is responsible for creating movies and managing and assigning actors to those movies. You are an Executive Producer within the company and are creating a system to simplify and streamline your process.
# Models:
Movies with attributes title and release date and actor
Actors with attributes name, age and gender
# Endpoints:
GET /actors and /movies
DELETE /actors/ and /movies/
POST /actors and /movies and
PATCH /actors/ and /movies/
# Roles:
Casting Assistant
Can view actors and movies
Casting Director
All permissions a Casting Assistant has and…
Add or delete an actor from the database
Modify actors or movies
Executive Producer
All permissions a Casting Director has and…
Add or delete a movie from the database
# Tests:
One test for success behavior of each endpoint
One test for error behavior of each endpoint
At least two tests of RBAC for each role

# Instructions to set up authentication
1. Login to auth0 account
   https://auth0.com
3. Create tenant
4. Create application
5. Create API
6. Create User
7. Create Role
   
# Steps to Deployment:
## Local Run:
### Prerequisite:
#### Git: 
Clone the Git repository: [git@github.com:sarbanibhadra/FSND_CapstoneV1.2.git](https://github.com/sarbanibhadra/FSND_CapstoneV1.2.git)
#### Install Postgres:
##### Mac/Linux
##### Install Postgres using Brew. Reference: https://wiki.postgresql.org/wiki/Homebrew 
*.  brew install postgresql*
#### Verify the installation:
*. postgres --version*

*. pg_ctl -D /usr/local/var/postgres start*

*. pg_ctl -D /usr/local/var/postgres stop*

#### Verify the database:
Open the psql prompt to view the roles, and databases:
##### Open psql prompt
*. psql [username]*
##### View the available roles
*. \du*
##### View databases
*. \list*

### Instructions to run the App in Local:
1. Create a project directory
3. Clone the starter repo inside the project directory

   *. git clone  [git@github.com:sarbanibhadra/FSND_CapstoneV1.2.git](https://github.com/sarbanibhadra/FSND_CapstoneV1.2.git)*
   
6. Create a virtual environment
   
   *. python3 -m venv myvenv*

   *. source myvenv/bin/activate*
8. Set up the environment variables
   
   *. chmod +x setup.sh*
   *. source setup.sh*

10. Install the Python dependencies

    *. pip install -r requirement.txt*
   
12. Run the app
    
    *. python3 app.py*

13. Application URL in local setup
    
    http://127.0.0.1:5000/

# Screenshots from Local Run:
1 Login screen
![image](https://github.com/sarbanibhadra/FSND_Capstone/assets/28161929/88f43bd1-6cd1-4e58-bb3e-557ebd1e58b0)
2.Login and password entry screen from auth0
![image](https://github.com/sarbanibhadra/FSND_Capstone/assets/28161929/0e707744-bb6b-43b2-844e-5b8f460ba3d2)
3.Home page
![image](https://github.com/sarbanibhadra/FSND_Capstone/assets/28161929/eb5e2791-5f8b-401a-b899-d988f31e5a05)
4. List of Movies page
![image](https://github.com/sarbanibhadra/FSND_Capstone/assets/28161929/50a907ad-c5e1-4068-bcdd-bb3f679a0199)
5. Add movies page
![image](https://github.com/sarbanibhadra/FSND_Capstone/assets/28161929/efca7c82-c013-4ee4-a5cf-0f3c68f0ae62)
6. Delete Movie page
![image](https://github.com/sarbanibhadra/FSND_Capstone/assets/28161929/73aa898c-f12c-4591-8dcf-e42897bd42b3)
7. Update Movie page
![image](https://github.com/sarbanibhadra/FSND_Capstone/assets/28161929/8706e3df-afc8-47c8-9d6d-6ca53fd4f1f1)
8. List of Actors page
![image](https://github.com/sarbanibhadra/FSND_Capstone/assets/28161929/222a967a-2b51-4786-86af-21196570d54f)
9. Add Actor page
![image](https://github.com/sarbanibhadra/FSND_Capstone/assets/28161929/73cb9416-1c2c-4276-bdf6-4be618b930ac)
10. Delete Actor page
![image](https://github.com/sarbanibhadra/FSND_Capstone/assets/28161929/a16aeb1e-8cc1-47dd-86af-d12817d57a9b)
11. Update Actor page
![image](https://github.com/sarbanibhadra/FSND_Capstone/assets/28161929/49b21c24-d853-4ef2-93a8-6e9ac4eede3a)
12 Logout screen
![image](https://github.com/sarbanibhadra/FSND_Capstone/assets/28161929/0cb49f6a-d3b9-4deb-81ec-ac36b9d074b0)

## Steps for deploying to Heroku
Here are the steps followed to deploy the code as Heroku app:
 1. Installed Heroku CLI in your local
    
    *. curl https://cli-assets.heroku.com/install.sh | sh*

    # Or, use Homebrew on Mac
    
    *. brew tap heroku/brew && brew install heroku*
    
 2. Verified the installation
     
    *. heroku --version*
 3. Verified the download
     
    *. which heroku*
 4. Logged at Heroku with your user name and password from dashboard from https://www.heroku.com/home

    *. heroku login -i*
 5. Initialized Git

     *. git init*
     
     *. git config --global user.email "you@example.com"*

     *. git config --global user.name "Your Name"*

     *. git add .*

     *. git status*

     *. git commit -m "your message"*
 7.  Created an App in Heroku Cloud

     *. heroku create [my-app-name] --buildpack heroku/python*

     *. git remote -v*
 8.  Added PostgreSQL addon for our database

      *. heroku addons:create heroku-postgresql:essential-0 --app [my-app-name]*
 9.  Configured the App

      *. heroku config --app [my-app-name]*
 10. Added additional Environment Variables from setup.sh. Go to your Heroku Dashboard in the browser and access your application's settings. You will have to go to the Heroku dashboard >> Particular App >> Settings >> Reveal Config Vars section. Add the variables.

 11. Pushed it to Git

      *. git push heroku HEAD:master*
 12. Ran migrations

     *. python manage.py db init*

     *. python manage.py db migrate*

     *. python manage.py db upgrade*

     *. heroku run python manage.py db upgrade --app [my-app-name]*
 13. Accessed the application at

  https://myfsnd-app-ccf72007e807.herokuapp.com/

  # Few Screenshots from Heroku Deployment:
  1 Login screen
  ![image](https://github.com/sarbanibhadra/FSND_CapstoneV1.2/assets/28161929/0e2476f6-ae53-4b8b-a6bf-c8576a4d3288)
  2.Login and password entry screen from auth0
  ![image](https://github.com/sarbanibhadra/FSND_CapstoneV1.2/assets/28161929/6abdd828-9543-4d31-be35-9683cba2ed04)
  3.Home page
  ![image](https://github.com/sarbanibhadra/FSND_CapstoneV1.2/assets/28161929/dc307b45-ced1-4c8c-908d-783145668d89)

     



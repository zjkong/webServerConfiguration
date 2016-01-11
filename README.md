# webServerConfiguration
Configured a web server on AWS to serve a catalog application

1 Ip address to access this application:

http://52.24.215.154/

2 The complete URL to my hosted web application:

http://ec2-52-24-215-154.us-west-2.compute.amazonaws.com/itemcatalog

3 Summary of configuration:

1) Generated private key from this link:https://www.udacity.com/account#!/development_environment
   and followed instructions in it then I can login into remote server as root user.

2) Created a new user grader with sudo permission by using 'visudo' command.

3) Generated key pair to replace password login as user grader locally.

4) Disabled password authentication.

5) Updated all packages by using 'apt-get update' and 'apt-get upgrade' commands.

6) Configured firewall only allow incoming connections for SSH (port 2200), HTTP (port 80), and NTP (port 123).

7) Configured the local timezone to Los Angeles time.

8) Installed apache2 in the remote server.

9) Created a directory in /var/www to place flask application and total structure is as followed:

|--------FlaskApp

|----------------FlaskApp

|-----------------------static

|-----------------------templates

|-----------------------venv

|-----------------------__init__.py

|-----------------------database_setup.py

|-----------------------sports_and_equipments.py

|-----------------------client_secrets.json

|----------------flaskapp.wsgi

  (1) Installed and enabled mod_wsgi.
  
  (2) Used 'git clone' to copy catalog application from github.
  
  (3) Installed flask and other packages including requests, sqlalchemy, psycopg2, oauth2client and json.
  
  (4) Configured and enabled New Virtual Host in '/etc/apache2/sites-available/FlaskApp.conf'.
  
  (5) Created the .wsgi File so Apache2 server can communicate with python application.
  
10) Added both ip address and web url to google console's Authorized JavaScript origins.

11) Created a new role catalog which has limited permission to psql database.(In my application, I granted select, insert, update and delete permission to new role)

12) Disabled remote login.

13) Restarted apache2 server to update all changes.

4 No third-party resources used in the configuration.

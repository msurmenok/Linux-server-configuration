# Linux-server-configuration
Information about configuration changes made for linux server to deploy a flask application.

## To connect via SSH
IP address: 34.210.97.152\
Port: 2200\
`ssh -i PRIVATE_KEY grader@34.210.97.152 -p 2200`
## To access web application
Web app is hosted at http://34.210.97.152/ on the standard port (80).
## Summary of installed software
Ubuntu packages:
- libapache2-mod-wsg
- postgresql
- postgresql-contrib

Python global packages:
- virtualenv

Packages in Python virtual environment:
- flask
- flask-sqlalchemy

## Summary of configuration changes made
### Security
- Created a new user and set ssh key, gave the new user sudo access
- Changed ssh port to 2200, closed all ports except 2200, 80, and 123.
- Disabled remote connection for *root*
- Set server timezone to UTC
- Checked that PostgreSQL is not available remotely
- Added a new PostgreSQL role without superuser privilege

### Deployment
- Installed a virtual environment and cloned Catalog Item project git repo
- Created a new database and populated it with data from the project
- Inside Flask app, changed settings to connect PostgreSQL
- Added an Apache configuration and wsgi configuration file



## List of resources:
- [tutorial about setting timezone](https://www.digitalocean.com/community/tutorials/how-to-set-up-timezone-and-ntp-synchronization-on-ubuntu-14-04-quickstart)
- [tutorial about deploying Flask app](https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps)
- [article about deploying Django](https://www.thecodeship.com/deployment/deploy-django-apache-virtualenv-and-mod_wsgi/)
to add packages from virtual environment to wsgi configuration file
- [tutorial about installing PostgreSQL](https://www.digitalocean.com/community/tutorials/how-to-secure-postgresql-on-an-ubuntu-vps)
- [how to change password in PostgreSQL](https://stackoverflow.com/questions/7695962/postgresql-password-authentication-failed-for-user-postgres)




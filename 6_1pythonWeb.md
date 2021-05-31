#Python app to web 

The task was completed as a part of the Python [course](https://terokarvinen.com/2021/python-web-service-from-idea-to-production/) by Haaga-Helia. The sources used for deployment are from Terokarvinen.com.

##Main phases
First, obtaining a virtual machine from Digital Ocean, creating a user, locking the root account, setting up the firewall and allow ports 22 and 80
Second, configuring apache2 to run on the system, along with the necessary python3 installs and postgresql
Third, create an administrative user, lock the account and join the group with main account, and give the right permissions
Fourth, edit the necessary conf-files for enabling the pythonapp to run. Documentation [here](https://terokarvinen.com/2020/deploy-python-flask-to-production/)
Fifth, test the app with hello world
Sixth, try with an app with modules and libraries to verify everything is instaleld
Seventh, create database user and table for the administrative account
Eight, enable the sql to work as a backend
Ninth, admire your site :) 

If you are interested, check out terokarvinen.com for MUCH more detailed information

## Problems and (maybe) solutions
First, failed to reach my site from external browsers - solution, hole in firewall port 80, type the correct address to avoid (my) ultimate rookie mistake :) 
Second, postgre complained about rights when creating my own user - solution -> see below (kind of)
Third, Apache failed to reach the hello.py, despite everything being installed, and everything double and triple checked. Solution: error log gave a vague clue about rights not being correct, and indeed the home directories had weirdly restrictive rights, in comparison to my virtual machine at home. Used chmod to give execute rights, and it worked.
Fourth, SQL didn't show up. Turns out one of the modules psycopg2 was missing. SOlution - install it
Fifth, the permissions in the beginning seems to have messed up my first users postgre, cant see the tables, and I don't know how to log in as the other user. Solution - must ask tomorrow.
Sixth, the sample data is replicated when relaunched. Solution: tried to add unique=True, but it didn't do much good. Must check tomorrow. At least it verifies the database works.

##Result

167.99.132.240 

(up and running 31.5.2021)

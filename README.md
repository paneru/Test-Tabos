TABOS
=======================

Introduction
------------
This is the TABOS project, based upon skeleton application using the ZF2 MVC layer and module
systems. 


Installation
------------

Using Ant 
----------------------------
First clone the repository into a folder, say, /var/www/TABOS:


```bash
cd /var/www/
git clone git@github.com:paneru/Test-Tabos.git
```

Then go into the build folder (in our example /var/www/TABOS/build) and copy the developer.properties.dist into developer.properties:

```bash
cd /var/www/bluebird/build
cp developer.properties.dist developer.properties
```

Next, edit the value in the new file developer.properties after creating two databases, say bluebird and bluebird_tests, adjusting the values according to your environment (note that the testUrl is taken from the virtual host example below, it needs to point to the test url):
Also note that the test database will be recreated for every test run so will not hold persistent data

```ini
# database
dbName=TABOS
dbHost=localhost
dbUser=xyz
dbPass=xyz_password

#test database
testDbName=TABOS_tests
testDbHost=localhost
testDbUser=abc
testDbPass=abc_password

testUrl=http://TABOS-test.localhost/
```


Finally, run the build script:

```bash
cd /var/www/TABOS/build
ant
```


    


Virtual Host
------------
Afterwards, for development, set up a virtual host, pointing to the public/ directory of the
project, with APPLICATION_ENV set to the type of checkout:

development:

```SetEnv APPLICATION_ENV "development"```

production

```SetEnv APPLICATION_ENV "production"```


For development installations, you also want to point a second virtual host to the same public folder using

```SetEnv APPLICATION_ENV "test"```

The corresponding url needs to be used for running unit tests and story tests. (see the above developer.properties)

Example host for test environment:


```
<VirtualHost *:80>
    ServerAdmin webmaster@localhost
    ServerName bluebird-test.localhost

    DocumentRoot /var/www/TABOS/public

    SetEnv APPLICATION_ENV "test"

    <Directory /var/www/TABOS/public>
        Options +Indexes FollowSymLinks MultiViews
        AllowOverride All
        Order allow,deny
        allow from all

    </Directory>

</VirtualHost>
```






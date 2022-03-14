---
layout: post
title: Jinqianbao
date: 2018-06-11
Author: Ali
categories: 
tags: [system, web]
comments: true
---



We can find many very useful tools on the Internet, especially some platforms such as GitHub. In many cases, Github will give installation steps, but usually in a complete system environment, which will waste resources to a large extent. In order to manage these disparate tools to the maximum extent, Docker can provide a good solution. Specifically, **Docker** can use minimal resources to complete the independent operation of each server.

This project aims to demonstrate how to fully save an open source project (web server) to your local network.



**Original project source: https://github.com/g0v/sunshine.cy/tree/master/website/cy by 駱勁成 thewayiam**



# Install ubuntu16.04 in WMware software

I believe you can do it 



# Docker installation under Ubuntu

-   ### root privileges

Sudo su

-   ### Install dependency packages

apt-get -y install \\

apt-transport-https \\

ca-certificates \\

curl

-   ### Add update source key

curl -fsSL <https://download.docker.com/linux/ubuntu/gpg> \| apt-key add -

-   ### write the update source address

> add-apt-repository \\
>
> \"deb \[arch=amd64\] <https://download.docker.com/linux/ubuntu> \\
>
> \$(lsb_release -cs) \\
>
> stable\"

-   ### Update

apt-get update

-   ### Install Docker

apt-get -y install docker-ce

-   ### Test

docker run hello-world



*Tip:*

*For other platform installation methods and some basic operation guides of Docker, please visit the reference documentation:*

*<http://www.runoob.com/docker/ubuntu-docker-install.html>*

# Configure ubuntu system under docker

-   #### Pull a ubuntu system from Dockerhub

> docker pull ubuntu:16.04
>
> docker run -it -p 8000:8000 ubuntu:16.04
>
> apt-get update

-   #### You may need to add sources to make sure the required packages can be downloaded If necessary

> apt-get install vim
>
> vim /etc/apt/sources.list

apt-get update

-   #### Install components

> apt-get install libxml2-dev libxslt1-dev python-dev libffi-dev
>
> apt install python-pip
>
> pip install lxml
>
> pip install Scrapy
>
> sudo apt-get install git python-pip python-dev python-setuptools postgresql libpq-dev



# **Deployment project file**

-   #### Clone the source code from github:

> git clone <git@github.com:thewayiam/cy.git>

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/jinqianbao/image002.jpg)

- #### This kind of error occurs because of the SSH connection problem, you can replace it with the following code:

> git clone [https://HYPERLINK \"https://github.com/thewayiam/cy.git\"github.comHYPERLINK \"https://github.com/thewayiam/cy.git\"/HYPERLINK \"https://github.com/thewayiam/cy.git\"thewayiam/cy.git](https://github.com/thewayiam/cy.git)



# Deployment web server environment

- #### Go to the \'cy\'\' folder directory

> cd cy/website/cy/

- #### Install the software package

> pip install -r requirements.txt



Tip:

requirements.txt contains all the frameworks required by the server,

including：Django==1.9.13，psycopg2==2.6.2，djangorestframework==3.3.1，django-filter==0.11，gunicorn==19.6.0，coverage==3.7.1，elasticsearch==1.6.0，django-haystack==2.4.0，django-debug-toolbar==1.5



# Dump all the data to local database

- #### Change the postgres login password:


> su postgres
>
> psql -U postgres
>
> postgres=#alter user postgres with password \'postgres\';
>
> postgres=#\\q

- #### Dump data

​	createdb -h localhost -U postgres cy

​	pg_restore \--verbose \--clean \--no-acl \--no-owner -h localhost -U postgres -d cy local_db.dump

-   #### Create a new \'local_settings.py\' under the cy/website/cy/cy/ file and add the following code:

> SECRET_KEY = \'**your password**\' \# put random string inside and don\'t share it with anybody.
>
> DATABASES = {
>
> ​		'default\': {
>
> ​		'ENGINE\': \'django.db.backends.postgresql_psycopg2\', \# Add \'postgresql_psycopg2\', \'mysql\',\'sqlite3\' or \'oracle\'.
>
> ​		'NAME\': \'cy\', \# Or path to database file if using sqlite3.
>
> \# The following settings are not used with sqlite3:
>
> ​		'USER\': \'postgres\',
>
> ​		\'PASSWORD\': \'postgres\',
>
> ​		\'HOST\': \'localhost\', \# Empty for localhost through domain sockets or \'127.0.0.1\' for localhost through TCP.
>
> ​		\'PORT\': \'\', \# Set to empty string for default.
>
> ​	}
>
> }
>
> DEBUG = False

-   #### Start the server

cy/website/cy : python manage.py runserver 0.0.0.0:8000

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/jinqianbao/image004.jpg)



Tips:

The command python manage.py runserver listens to 127.0.0.1:8000 by default But the address 127.0.0.1 is a loopback address and cannot be accessed externally.

So we need to specify the listening port python manage.py runserver 0.0.0.0:8000, where 0.0.0.0 means listening to all addresses.



# Apache deployment

Django has only one server for debugging, and does not provide a server for production environments. So we also need to deploy the django project to the apache server.

-   #### Install apache2

apt install apache2

-   #### Install Web Server Gateway Interface

apt-get purge libapache2-mod-wsgi

apt-get install libapache2-mod-wsgi

a2enmod wsgi

-   #### Restart apache2

service apache2 restart



Tip：when you restart apache2 it may report **ServerName error**,you need to add \"ServerName 127.0.0.1\" in /etc/apache2/apache2.conf file



-   #### Create a new website configuration file \'xxxxx.conf\' and add the following code:

vim /etc/apache2/sites-available/xxxxxx(anyname).conf



```
<VirtualHost *:8000>

 

​		Alias /search/ /cy/website/cy/search/                  

​		<Directory /cy/website/cy/search>         

 	   Require all granted

​	  </Directory>

WSGIScriptAlias / /cy/website/cy/cy/wsgi.py       

​		<Directory /cy/website/cy/cy>          

  <Files wsgi.py>

​    Require all granted

  </Files>

  </Directory>

</VirtualHost>
```



-   #### set the listening port to port 8000 in \"/etc/apache2/ports.conf\"

-   #### Modify the cy/website/cy/cy/wsgi.py file as follows

> ```
> import os
> 
> from os.path import join,dirname,abspath
> 
> 
> PROJECT_DIR = dirname(dirname(abspath(\_\_file\_\_)))
> 
> 
> import sys
> 
> sys.path.insert(0,PROJECT_DIR)
> 
> 
> from django.core.wsgi import get_wsgi_application
> 
> 
> os.environ.setdefault(\"DJANGO_SETTINGS_MODULE\", \"cy.settings\")
> 
> 
> application = get_wsgi_application()
> ```
>
> 

-   #### Execute permission settings for website directory scripts under Apache

> cd /cy/website
>
> sudo chmod -R 644 cy
>
> sudo find cy -type d \| xargs chmod 755



**Tips：**

View the apache error log : cat /var/log/apache2/error.log

After executing the above command, check the error file and find that the /root/cy file lacks the execution command, we can execute chmod +x /root/ to see if the folder has execute permissions



# Publish the packaged docker

- #### Packaging the docker container


docker commit -a \"xxx\" -m \"jinqianbao\" xxxxxx（your Container ID） **jinqianbao**

docker save xxxxxx（image ID） \> /root/Desktop/jinqianbao.tar

- #### You can redeploy it on your cloud or other environment


> docker load \< /home/xxxx/Desktop/jinqianbao.tar
>
> docker run -it -p 8000:8000 906105104f34
>
> cd /cy/website/cy
>
> service postgresql restart

***Please wait a minute, it will take a while for the database to start up***

> python manage.py runserver 0.0.0.0:8000
>
> service apache2 start



**Tips：**

Release the occupancy of port 8000：lsof -t -i tcp:8000 \| xargs kill -9





# Debug html code（option）

- #### After the server runs successfully, you will find that there are still some css or js files loaded from other servers. 

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/jinqianbao/image016.jpg)



![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/jinqianbao/image022.jpg)

- #### Downloaded those js or css files from the website and put them into static folder.

​			docker cp xxxxxxx

​			chmod 777 static 

- #### Search for these tags in local files on the web server

​			find .\|xargs grep -ri \"amazonaws\"

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/jinqianbao/image018.jpg)

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/jinqianbao/image020.jpg)

- #### Change the file path

- #### Also pay attention to commenting out some useless code. Like in ./templates/base.html:

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/jinqianbao/image010.jpg)

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/jinqianbao/image012.jpg)

- #### Refresh

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/jinqianbao/image028.jpg)



Tips：

Find if all files in a directory contain a certain string ：find .\|xargs grep -ri \"IBM\"

Find if all files in a directory contain a certain string, and only print out the file name ：find .\|xargs grep -ri \"IBM\" -l




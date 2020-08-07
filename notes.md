# Wordpress Notes

Env:

 - Linux Mint ~18
 - VS Code
 - Docker Compose 
 - Wordpress setup 

***
Step 1

Setup a `docker-compose.yml` File like here:

 

     version: '3.3'
    
    services:
       db:
         image: mysql:5.7
         volumes:
           - db_data:/var/lib/mysql
         restart: always
         environment:
           MYSQL_ROOT_PASSWORD: somewordpress
           MYSQL_DATABASE: wordpress
           MYSQL_USER: wordpress
           MYSQL_PASSWORD: wordpress
    
       wordpress:
         depends_on:
           - db
         image: wordpress:latest
         ports:
           - "8000:80"
         restart: always
         environment:
           WORDPRESS_DB_HOST: db:3306
           WORDPRESS_DB_USER: wordpress
           WORDPRESS_DB_PASSWORD: wordpress
           WORDPRESS_DB_NAME: wordpress
    volumes:
        db_data: {}
[Code Source - Hostinger - Run Docker Wordpress ](https://www.hostinger.com/tutorials/run-docker-wordpress)

***

Step 1.1

Start the Docker Container with:

    docker-compose up -d


***
Step 2

Install VS Code Extension "Docker ":
 `ms-azuretools.vscode-docker`
***
Step 3

Navigate to the Docker Menu Point in VS Code, then choose the right container 
-> Attach Visual Studio Code

![like here ](https://github.com/GaboCapo/WordpressToolset/blob/master/rsc/vscode1.png)

***
Step 4

Wordpress files are kept inside the `container`, for example you can find `wp-content` at:

```
/var/www/html/wp-content
```

But, to get "inside" your running container you will have to do something like `docker container exec -it <your_container_name> bash`. More here: [How to get into a docker container?](https://stackoverflow.com/questions/30172605/how-to-get-into-a-docker-container)
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjEyNDUwMTk3MCwxMTU4NDkwNDg4LC0zNj
IyNTMzMDEsLTEwMDk2MzIwMSwtNzQ5ODU1MDk0XX0=
-->
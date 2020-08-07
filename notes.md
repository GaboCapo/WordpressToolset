# Wordpress Notes

Env:

 - Linux Mint ~18
 - VS Code
 - Docker Compose 
 - Wordpress setup 

***
Step 1
Setup a `docker-compose.yml` File like here:


***
Step 2
Instal VS Code Extension "Docker ":
 `ms-azuretools.vscode-docker`
***
Step 3


***
Step 4
Wordpress files are kept inside the `container`, for example you can find `wp-content` at:

```
/var/www/html/wp-content
```

But, to get "inside" your running container you will have to do something like `docker container exec -it <your_container_name> bash`. More here: [How to get into a docker container?](https://stackoverflow.com/questions/30172605/how-to-get-into-a-docker-container)
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTc2ODA0MDc0NSwtMTAwOTYzMjAxLC03ND
k4NTUwOTRdfQ==
-->
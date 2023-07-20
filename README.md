# symfony-docker

Fork from https://github.com/dunglas/symfony-docker/, but without the fancy https stuff, for simpler applications.
A minimal Symfony project for creating applications from scratch.
Contains:
php + mysql + phpmyadmin + nginx.

Required:
- Docker Engine
- docker-compose plugin
- php 8.1

**CONFIGURATION**
1. ``sudo nano /etc/hosts/``
2. add this address:
   ``127.0.0.1       your-project.symfony``

**INSTALLATION**

1. clone the repository
2. go to the pulled repo root ("/symfony-docker")
3. ``docker-compose build``
4. ``docker-compose up -d``
4. ``docker-compose exec php bash``
5. ``composer install``
6. ``exit``

After Installation, in order to start the project, use command in root directory ("/symfony-docker):

``` docker-compose up -d```

In order to stop the project, use command:

``` docker-compose stop```

sites:
- your-project.symfony:8080 -> app
- your-project.symfony:8081 -> phpmyadmin

If you work on linux and cannot edit some of the project files right after the first installation, you can run 
```docker compose run --rm php chown -R $(id -u):$(id -g) .``
 to set yourself as owner of the project files that were created by the docker container.

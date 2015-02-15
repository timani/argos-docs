Box: A Docker bundle for local development
=================

A light sandbox Docker image for PHP web development. Easily scale and customize the components (web server, database, redis, Varnish, etc ) as you need to.

![Docker logo](http://upload.wikimedia.org/wikipedia/commons/7/79/Docker_(container_engine)_logo.png "Docker logo")


This image with comes built with nginx, PHP-FPM, Drush, MySQL, Redis, Varnish and can be easily extended

## Documentation

Naboo wedge jawa coruscant dooku naboo mon. Darth mandalore lobot c-3p0 hutt naboo droid jango organa. Antilles anakin skywalker mandalorians calamari jar tusken raider k-3po organa.

#### Table of Contents
* [Getting Started](#)
* [Installation](#)
* [Components](#)
* [Workflow](#)
* [Uninstallation](#)
* [Contribution](#)

## Quickstart

The easiest way to get started is to use the fig and this will automatically build and run your containers.

<strong>Build:</strong><br />
<code>fig up -d</code><br />

## Manual installation

In case you need to manually create the containers. Each component can be manually started and run separately, for example this is how to start the full Box.

**Database**

<code>docker run -d -t -p 3306:3306 --name mysql --volumes-from mysql_data dicix/mysql</code>

**Web server**

<code>docker run -d -t -p 8080:8080 --name nginx --link mysql:db -v /Users/dicix/work/www/proiecte:/var/www/html dicix/nginx</code><br />

**Redis**

<code>docker run -d -p 6379:6379 --name redis dicix/redis</code>

**Varnish**

<code>docker run -d -t -p 80:80 --name varnish dicix/varnish</code>

### Connecting to a container and executing commands

To connect to a container you can use the `docker exec` command to attach and perform commands like debugging error logs within the container.

<code>docker exec -it nginx /bin/bash</code>

## Contributing
We encourage you to fork the project and create a pull request if you have any bug fixes or enhancements. For more information you can review the [contribution guidelines](#).

## License
We are now looking into mithe already running container to see if there is a newer image downloaded. If there is a newer we stop the old  [MIT](#) license.

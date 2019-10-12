# Docker-WordPress

Barebones Docker config for a WordPress theme and plugin development

## Getting started

After checking out this repo, and assuming you have installed Docker, just run:

`docker-compose up -d`

When it is done booting, you can browse to http://localhost:8000 and you will see the initial WordPress install screen.

Now you're ready to start developing.

* Add plugins to the `plugins` directory each in their own directory.
  * Example)  docker-wordpress/plugins/my-plugin/
* Add themes to the `themes` directory each in their own directory
  * Example)  docker-wordpress/themes/my-theme/

You can browse the database by with these settings:

```
Hostname: localhost
Username: wordpress
Password: wordpress
DB Name: wordpress

Root Password: somewordpress
```


## To stop container run:

`docker-compose down`


## To view log files:

`docker-compose logs -f`


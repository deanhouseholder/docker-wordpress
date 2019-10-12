# Docker-WordPress

Barebones Docker config for a WordPress theme and plugin development



## Getting Started

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
Port: 3306

Root Password: somewordpress
```



## To stop container run:

`docker-compose down`



## To view log files:

`docker-compose logs -f`



## Database Management

### Refresh DB

If you want to refresh the database (reset it back to new install), run:

`docker-compose down`
`docker volume rm docker-wordpress_db_data`


### Backup DB

To back up the database, run:

`docker exec docker-wordpress_db_1 mysqldump -u root -psomewordpress myapp > dump.sql`


### Restore DB

To restore the database, run:

`docker exec -i docker-wordpress_db_1 mysql -u root -psomewordpress myapp < dump.sql`



## Notes

You'll notice after starting WordPress it will copy the default plugins and themes from a base WordPress install into your `plugins` and `themes` directories. This is fine. You can safely ignore or delete them (except don't delete your default theme.)


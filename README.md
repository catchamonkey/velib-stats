# Velib Stats

This application allows to display some statitics about velib bike rental
system stations.

## Install:

1. Play with your command line:

    $ git clone git://github.com/marcw/velib-stats.git
    $ cd velib-stats
    $ git submodule update --init

2. You will need to edit the `web/.htaccess` file and change the database
settings.

3. Import all the files present in `sql/`:in your database. There are no
   database user info in the dump, you must be the database owner to create the
   project's schema. The database needs the PlPgsql language. The objects will
   be stored in a vlib schema. If you have an existing schema vlib in your
   database you will need to edit the dump and re-generate model files.

    => \i /absolute/path/velib-stats/sql/schema.sql

4. The project is ready to run!

## How To

### Import data

Importing data from Velib webservices to your databse is pretty easy.
Everything is done by calling your application.

1. In order to retrieve the station list, request with a GET method the following
uri: `http://your.host/update/list`

2. To update data for a particular station, request with a GET method the following
uri: `http://your.host/update/id`. `id` should be replaced with correct id of
station.

### Clear the cache

Fire a console and type

    $ cd path/to/the/project
    $ rm -rf cache/*

Depending on your configuration, you might need to have superuser rights.

## License

This application is licensed under the MIT license.

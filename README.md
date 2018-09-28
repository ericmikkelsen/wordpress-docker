# wordpress-docker
Docker Setup for Wordpress

## 1 Setup .env file

Copy the `.env.example` file and rename it `.env`

Your .env file has 5 variables, I like to keep everything the same. for example, this file from pierogi heaven

```
PROJECT_ID=pierogi_heaven

# MYSQL
MYSQL_DATABASE=pierogi_heaven
MYSQL_ROOT_PASSWORD=pierogi_heaven
MYSQL_PASSWORD=pierogi_heaven
MYSQL_USER=pierogi_heaven
```

### Security

*DO NOT do this* on production or any live sites. These instructions are simply for running a local copy of your content.

## 2 Docker

Once your `.env` file is set, run `docker-compose up`

## Get mysql database

Skip this step if the site doesn't exist yet, or isn't running wordpress yet.

If your site is running wordpress already and you want to work on it locally. 

1. Go to the site, sign in
2. Install the [migrate db plugin by delicious brains](https://wordpress.org/plugins/wp-migrate-db/).
3. Access the “Migrate DB” menu option under Tools (or under Settings on multsite intallations)
4. add this to the first replace input `//localhost:8080`
5. add this to the second replace input `/var/www/html`
6. Hit the blue "Export and save" button and save the zip file.

## Import the database to your local phpmyadmin

Go to [localhost:8181](http://localhost:8181), you should be logged in already, and import the recently saved zip file into the database already present. It should be named whatever you entered into the `.env` file for `MYSQL_DATABASE`.

## WORDPRESS HAPPENED!

Hopefully. If everything went as planned, you can go to [localhost:8080](http://localhost:8080), and you should be able to see your wordpress install working just fine.

## Add Themes and Plugins

You can add themes to your themes directory and plugins to your plugins directory.
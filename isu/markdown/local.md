<img src="../images/IXM-Transparent-Vertical.jpg" style="float:right; margin:-10px 15px 0 0;" height="90" />
![Indiana State University logo](../images/isu_logo.png)

# Setting up local copy of ISU site

1. [MAMP](#mamp)
2. [Place site in document root](#place-site-in-document-root)
3. [Create database](#create-database)
4. [Import the database dump](#import-the-database-dump)
5. [Copy settings.php](#copy-settingsphp)
6. [Navigate to Drupal](#navigate-to-drupal)

## MAMP

Download and install MAMP: [www.mamp.info](http://www.mamp.info/en/index.html)

If you prefer, there is a good video explaining how to download and install MAMP: [drupalize.me/videos/installing-mamp-web-server](http://drupalize.me/videos/installing-mamp-web-server)

## Place site in document root

You can do this one or two different ways. You can set the MAMP document root to the parent directory or the actual directory of the ISU repository, or you can move the repository into the MAMP's document root, or you can do a combination of both. The MAMP document root is effectively the web root of the local server.

You can change the MAMP document root by opening MAMP, selecting "Preferences", and then by changing the document root setting under the "Apache" tab in the "Preferences" window.

![alt text](http://o7.no/11zURms "MAMP document root")

If you don't change your document root and instead move your copy of the ISU Drupal site that you forked on Github into the MAMP root, by default it will be located at: /Applications/MAMP/htdocs


## Create database

Drupal requires a database to be created in order to install and run it. From the MAMP start page you can click the phpMyAdmin tab. Inside PHPMyAdmin select "Databases". From there, create a new database with the name 'isu_primary'.

![alt text](http://o7.no/11zUI2i "Create database")

## Import the database dump

[stage.tar.gz](https://dl.dropboxusercontent.com/u/57694/imagex/isu_docs/stage.isu.ixm.ca_20130513_112752.sql)

From within the database that you created, navigate to the "Import" tab in phpMyAdmin. Download the preceding database dump from stage.isu.ixm.ca and select it as the file to import into the database. Click "Go" at the bottom.

![alt text](http://o7.no/10uBnbD "Import dump")

If all goes well, this will fill out your database with a copy of the staging database.


## Copy settings.php

[settings.php](https://dl.dropboxusercontent.com/u/57694/imagex/isu_docs/settings.php)

Download the above file and place it in the Drupal repository in the directory /sites/default/. This file is the configuration file that provides the information to connect to the database.

![alt text](http://o7.no/12vPT5G "Place settings.php")

This settings.php file has been provided with a default configuration that should work provided your MAMP settings are their defaults and you created the database with the same name as the instruction defines above. If these things are not true, the database connection configuration in settings.php will have to be changed to match your environment.


## Navigate to Drupal

Make sure the MAMP server is running and navigate to the root of the site in the directory your site resides within in your browser. By default, this will be:

localhost:8888

If you've placed the repository inside another directory inside of the document root, the default will be:

localhost:8888/[YOUR DIRECTORY]

Since you're using a copy of the database from the staging environment, you do not have to go through the installation process and all of the site's modules and configurations should match those that are setup in the staging site.

However, on the flip side this means that some things will be broken because the site's file assets are stored in neither the codebase nor the database. Instead, they reside in their own directory. As a result, once you get the site working, any images or other content-based files that are included in the site will be broken because they are missing. To fix this, you can download the following and extract its contents as a directory called "files" in the same /sites/defaut/ directory that you placed settings.php in.

[files.zip](https://dl.dropboxusercontent.com/u/57694/imagex/isu_docs/files.zip)

## Discussion

This is sort of a piecemeal way of getting the site setup on your local machine from the various components in use. In some cases it takes shortcuts, and in others it's somewhat indirect. Keep this in mind. This is just one way.

That said, these instructions should be illustrative of general structures and necessities of working with Drupal. For instance:

- Drupal needs a database to be installed.
- Drupal's file structure is such that an individual site's configuration usually resides in /sites/default.
- Drupal's database connection configuration resides in settings.php.
- Files in Drupal are not stored in the database and, as a matter of best practice, are not included in the repository.

Other ways we could approach this are:

- Take a complete archive of the site's files on stage and just have you download it and place it in the document root (you'd still need to create a database and import the database dump).
- Install the Drupal site from scratch using the codebase. This would require quite a bit more configuration on your end.













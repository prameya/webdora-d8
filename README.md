# Deploying Drupal 8 on Google App Engine and Cloud SQL

THIS README IS NOT COMPLETE.

Go to https://github.com/drupal-composer/drupal-project and download the default composer.json file. 
We will use this to create our app and deploy it to google app engine

In an empty folder down the composer.json. We will be initializing our project here.

If you want to know how to use it as replacement for
[Drush Make](https://github.com/drush-ops/drush/blob/8.x/docs/make.md) visit
the [Documentation on drupal.org](https://www.drupal.org/node/2471553).

## Usage

Git init

https://github.com/codepath/ios_guides/wiki/Using-Git-with-Terminal

Edit the composer.json file to make it suitable for our use. We are not going to need multiple sites or local env file configuration for this tutorial.

Notice the changes we made. We added php7.2.x and ext-gd— the gd module is still finicky on the app engine, so instead of using a set version, we will allow gcloud to figure it out by using the wildcard “*” for the version.

Then you do composer create-project

Then do composer install -v

Then composer update -v

Now you should have a Drupal install showing up
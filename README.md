# Deploying Drupal 8 on Google App Engine and Cloud SQL
THIS README IS NOT COMPLETE.
More information/description about this project should be inserted here.

## Quickstart

The easiest way to get started is to clone this repo in your dev environment.

It is assumed that you already have a webserver installed and configured to use your project's `web` folder as the document root. See the Prerequisites section for more information.

```
use `git clone https://github.com/prameya/webdora-d8.git`
or `git clone git@github.com:prameya/webdora-d8.git`
then we create the project `composer create-project`
this will install all the required files
we will do the follow 2 steps to make sure everything is synced and linked
`composer install -v`
`composer update -v`
visit http://localhost to finish drupal installation
```
### Prerequisites

THIS SECTION IS NOT COMPLETE.

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

Go to https://github.com/drupal-composer/drupal-project and download the default `composer.json` file. 

We will use this to create our app and deploy it to google app engine

In an empty folder down the `composer.json`. We will be initializing our project here.

## Usage

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

Go to https://github.com/drupal-composer/drupal-project and download the default `composer.json` file. 

We will use this to create our app and deploy it to google app engine

In an empty folder down the composer.json. We will be initializing our project here.

`git init`

https://github.com/codepath/ios_guides/wiki/Using-Git-with-Terminal

Edit the composer.json file to make it suitable for our use. We are not going to need multiple sites or local env file configuration for this tutorial.

Notice the changes we made. We added `php7.2.x` and `ext-gd` the gd module is still finicky on the app engine, so instead of using a set version, we will allow gcloud to figure it out by using the wildcard `“*”` for the version.

Then you do `composer create-project`

Then do `composer install -v`

Then `composer update -v`

Now you should have a Drupal install showing up on http://localhost (depending on your config/setup).
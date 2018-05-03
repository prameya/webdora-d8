# Deploying Drupal 8 on Google App Engine and Cloud SQL
THIS README IS NOT COMPLETE.

More information/description about this project should be inserted here.

#### Assumptions
```
This project assumes you are using a Mac OS X system, with root/admin privilages.
```

## Quickstart
The easiest way to get started is to use `composer create-project`. You should have a web server preconfigured to use our project `webdora-d8/web` folder as the document root.

Use `git clone https://github.com/prameya/webdora-d8.git` or `git clone git@github.com:prameya/webdora-d8.git` to clone this project on your dev environment.

We will then initialize and install the application using composer.

Run steps below make sure everything is synced and linked.

```
composer install -v
composer update -v
```
If everything is configured properly then you should see the Drupal 8 installation page on http://localhost. Follow instructions on the screen to finish setting up drupal.

Now we are finally ready to deploy our app.

```
gcloud app deploy --verbosity=info
```
After deployment you can access your new drupal app engine app at:

```
https://your-project-name.appspot.com
```
### Prerequisites

THIS SECTION IS NOT COMPLETE.

You should have a web server (probably apache) installed and configured on your dev environment. If you do not already have necessary components installed use the steps below or follow the instractions at -- `https://getgrav.org/blog/macos-sierra-apache-multiple-php-versions`.

#### Install XCode CLI tools
`xcode-select --install`

#### Install Homebrew
`ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

To make sure brew installed use `brew --version`. To be safe, let's run `brew doctor`.

#### Install Apache
`brew install httpd`

To autoload apache on boot use `sudo brew services start httpd`

Use the following commands as needed:

```
sudo apachectl start
sudo apachectl stop
sudo apachectl -k restart
```
#### Install PHP
`brew install php@7.2`

#### Configure Apache for PHP
Edit the apache config file at `/usr/local/etc/httpd/httpd.conf` with your settings. See the guide linked on the top of this section for detailed setup guide. We also need to enable some modules. `LoadModule rewrite_module lib/httpd/modules/mod_rewrite.so`.

#### Install Google Cloud SDK and tools
Make sure we have python 2.7 installed `python -V`. We will use homebrew to install GCP SDK `brew cask reinstall google-cloud-sdk`. 

#### Brew update and clean up
```
brew update
brew upgrade
```
THIS SECTION IS NOT COMPLETE.

## Usage

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

Go to `https://github.com/drupal-composer/drupal-project` and download the default `composer.json` file.

We will use this to create our app and deploy it to google app engine

In an empty folder down the `composer.json`. We will be initializing our project here.

`git init`

Edit the `composer.json` file to make it suitable for our use. We are not going to need multiple sites or local .env file configuration for this tutorial.

Notice the changes we made. We added `php7.2.x` and `ext-gd` the `gd` module is still finicky on the app engine, so instead of using a set version, we will allow `gcloud` to figure it out by using the wildcard `“*”` for the version.

Then you do `composer create-project`

Then do `composer install -v`

Then `composer update -v`

Now you should have a Drupal install showing up on `http://localhost` (depending on your configuration and setup).

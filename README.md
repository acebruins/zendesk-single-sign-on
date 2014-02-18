# Zendesk single sign on example

This is a very basic Rails app to test Zendesk's single sign on.

## Setup

* git clone https://github.com/wiseleyb/zendesk-single-sign-on
* bundle
* be rake db:create db:migrate db:seed db:test:prepare
* bundle exec rails s
* login: admin 1234

## To host on Heroku
Since Zendesk single sign requires a live url it's easiest to play around with this on Heroku.

* gem install heroku
* heroku login
* heroku create (not the url it gives you)
* make sure you've add ~/.ssh/id_rsa.pub to your authorized keys on your heroku account
* git push heroku master
* heroku run rake db:migrate
* heroku run rake db:seed
* you should now be able to go to the url and login with admin / 1234
* change your admin password

### Set your Zendesk EVN variables
* heroku config:set ZENDESK_SHARED_SECRET= ...
* heroku config:set ZENDESK_SUBDOMAIN= ...

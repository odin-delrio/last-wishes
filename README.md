# Last Wishes - DDD Sample Application

[![Build Status](https://secure.travis-ci.org/dddinphp/last-wishes.svg?branch=master)](http://travis-ci.org/dddinphp/last-wishes)

## Add hosts to local machine
    sudo -- sh -c "echo 127.0.0.100 last-wishes.local >> /etc/hosts"
    sudo -- sh -c "echo 127.0.0.101 csrf-attacker.local >> /etc/hosts"
    
## Install assets
    bower install

## Set up the project
    curl -sS https://getcomposer.org/installer | php
    php composer.phar install

## Create the database schema
    php bin/doctrine orm:schema-tool:create

## Run your Last Will bounded context
    php -S last-wishes.local -t src/Lw/Infrastructure/Ui/Web/Silex/Public

## Notify all domain events via messaging
    php bin/console domain:events:spread

## Notify all domain events via messaging to another new BC deployed
    php bin/console domain:events:spread <exchange-name>

## Exercises

For the DDD learners, I propose you some exercises to practice your skills.

### UserRepository running with Redis

The default project uses Doctrine and SQLite to persist users, however, we would like to easily change the persistence storage to use Redis. The PRedis dependency is already specified in the composer.json file.

### UserRepository running with MongoDB

The default project uses Doctrine and SQLite to persist users, however, we would like to easily change the persistence storage to use MongoDB.

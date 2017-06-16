# Installation


1. Build/run containers with (with and without detached mode)

  $ docker-compose build
  $ docker-compose up -d

2. Update your system host file (add symfony.dev)

# UNIX only: get containers IP address and update host (replace IP according to your configuration)
$ docker network inspect bridge | grep Gateway

# unix only (on Windows, edit C:\Windows\System32\drivers\etc\hosts)
$ sudo echo "171.17.0.1 symfony.dev" >> /etc/hosts

3. Prepare Symfony app

  i. Update app/config/parameters.yml
  ii. Composer install & create database
      $ docker-compose exec php bash
      $ composer install
      # Symfony2
      $ sf doctrine:database:create
      $ sf doctrine:schema:update --force
      $ sf doctrine:fixtures:load --no-interaction
      # Symfony3
      $ sf3 doctrine:database:create
      $ sf3 doctrine:schema:update --force
      $ sf3 doctrine:fixtures:load --no-interaction
      
4. Enjoy: http://symfony.dev



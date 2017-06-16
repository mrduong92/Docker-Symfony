# Installation


1. Build/run containers with (with and without detached mode)

  $ docker-compose build
  $ docker-compose up -d

2. Update your system host file (add symfony.dev)

- Get Container IP:
$ docker network inspect bridge | grep Gateway

- Update Virtual hosts:
$ sudo echo "171.17.0.1 symfony.dev" >> /etc/hosts

3. Prepare Symfony app

  i. Update app/config/parameters.yml
  
  ii. Composer install
  
      $ docker-compose exec php bash
      
      $ composer install
      
4. Enjoy: http://symfony.dev



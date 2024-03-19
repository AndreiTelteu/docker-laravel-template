
## Docker usage on local environment

```bash

# create and start
./dc up
# stop
./dc stop
# start
./dc start

# install dependencies / composer install
./dc ci

# exec inside the php container
./dc php

# run migrations and seeders
./dc a migrate:fresh --seed
# run any artisan command
./dc a {command}

# install new php package
./dc c require package/name

# open tinker
./dc tinker

# open mysql client
./dc mysql

# import mysql dump
./dc exec -T db "mysql -h db -u laravel -psecret laravel" < dump-file_name.sql

# make storage link
./dc link

# recreate (to apply modifications in docker-compose.yml)
./dc recreate
./dc recreate php

# rebuild (to apply modifications in Dockerfile)
./dc build
./dc build php

```

## New laravel project

```
./dc up
./dc php "composer create-project laravel/laravel=10.* laravel"
sh -c "rm -rf laravel/README.md ; mv laravel/* . ; mv laravel/.e* . ; mv laravel/.g* . ; rm -rf rm -rf laravel;"
./dc a migrate
```

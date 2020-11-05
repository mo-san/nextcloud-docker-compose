# nextcloud-docker-compose

forked from [myoshimi/nextcloud-docker-compose](https://github.com/myoshimi/nextcloud-docker-compose)

====

Nextcloud with HTTPS reverse proxy by nginx, controlled upon docker-compose.

Intended to be used in Ubuntu on Raspberry Pi.

# Prerequirements

* Prepare two key files shown below to provide HTTPS connection.
    * SSL Certificate file (e.g. fullchain.pem)
    * SSL Certificate key file (e.g. privkey.pem)
    * Typically, these files can be obtained by ```certbot``` command which gets certificate by let's encrypt.

# Usage

``` shell script
git clone https://github.com/mo-san/nextcloud-docker-compose
cd nextcloud-docker-compose
echo "PATH_FULLCHAIN=/path/to/fullchain.pem" >> ./.env # e.g. /etc/letsencrypt/live/example.com/fullchain.pem
echo "PATH_PRIVKEY=/path/to/privkey.pem" >> ./.env # e.g. /etc/letsencrypt/live/example.com/privkey.pem
echo "PATH_DATA=/path/to/data_directory" >> ./.env # e.g. ./data/
echo "PATH_DB=/path/to/database_directory" >> ./.env # e.g. ./db/
docker-compose up -d
```

You need to have those environment variables written in the `.env` file, which is read by docker-compose.

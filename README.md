# Nextcloud + Onlyoffice all-in-one Docker-compose

You can use the configuration in the nextcloud folder to have a nextcloud instance with a onlyoffice configured on your homeserver.
This configuration uses a nginx container and the letsencrypt-nginx-proxy-companion. Both are in the docker-compose.yml in the proxy folder.

Before using this, you need to set the variables in `nextcloud/.env` and `nextcloud/db.env`.

Nextcloud will then be available at *https://nextcloud.YOUR_DOMAIN*. You need to configure the onlyoffice plugin on nextcloud with theses settings:

> Document Editing Service address: *https://onlyoffice.YOUR_DOMAIN*
> Secret key (leave blank to disable): *The JWT_SECRET variable in the .env file*
> Advanced server settings > Server address for internal requests from the Document Editing Service : *https://nextcloud.YOUR_DOMAIN*

You should start the nextcloud docker-compose instance before the proxy one, since the letsencrypt companion needs to detect what requests to do.
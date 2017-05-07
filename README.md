# dockerized-magento
Dockerized Magento example. Running Magento in a stack includes Nginx/PHP-FPM web server, Mysql, Redis, Varnish.
# Debugging with PHPSTORM
1. Find your host machine IP by running `ifconfig` (Mac, Linux) or `ipconfig` on Windows and add the value to `XDEBUG_REMOTE_HOST` environment variable in `docker-compose.yml`
2. Create a file named `server.location` in `Magento root/var/nginx/` and put in that the line
...`server_name your_virtual_host_url;` Ex: `server_name test.local;`
3. Xdebug is configured to listen on port 9009, not the default 9000 (to avoid conflict with PHP-FPM). In PHPSTORM > Prefences > Languages & Frameworks > PHP > Debug, change the Debug port to 9009
4. Also in PHP section > Servers, add a new server with name and host are same as the one in step 2. Check the option `User path mappings` and edit the `Absolute path on server` to `/var/www/html`
5. Install the Xdebug bookmarlets so we can start and stop the debugging from browser. Link here https://www.jetbrains.com/phpstorm/marklets/

Happy debugging!

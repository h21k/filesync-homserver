# filesync-homserver
docker-compose+proxy+nginx+db+nextcloud filesync docker network for the Raspberry Pi(3)
refined and based on previous work by: https://github.com/ichiTechs/Dockerized-SSL-NextCloud-with-MariaDB<br>

This is for the Raspberry Pi Arm architechture above only works on intel chipsets.

Resources:<br>
   - https://github.com/nextcloud/docker
   - https://github.com/jwilder/nginx-proxy
   - https://github.com/JrCs/docker-letsencrypt-nginx-proxy-companion
   
First create a docker network:

    -$ docker network create nginx-proxy
  
Start the database first:

    -$ docker-compose up -d db
  
Then start the rest of the network:

    -$ docker-compose up -d
    
Alternetively, use with out flag to see what is going on (make a screen first to detach):

    -$ screen
    -$ docker-compose up -d
    
Once this is running it may take a while for LetsEncrypt to get the certs...

Shutdown and or update the network:

    -$ docker-compose down (stops and removes these containers)
    -$ docker-compose pull (pulls the new updated images)
    -$ docker-compose up -d (starts your containers with the new updated images)


1. Docker basic command
docker run ubuntu /bin/echo 'Hello world'
docker run -i -t --rm ubuntu /bin/bash
docker run --name daemon -d ubuntu /bin/sh -c "while true; do echo hello world; sleep 1; done"
docker ps -a
docker logs -f daemon
docker stop daemon
docker ps -a
docker start daemon
docker ps -a 
docker stop daemon
docker rm <your first container name>
docker rm daemon
docker rm -f $(docker ps -aq)


2.  
docker run -d --name "test-nginx" -p 8080:80 -v $(pwd):/usr/share/nginx/html:ro nginx:latest
docker inspect test-nginx
docker inspect containername |  jq -r '.[0].NetworkSettings.IPAddress'
docker inspect containername --format='{{.NetworkSettings.IPAddress}}'

3.
https://github.com/collabnix/dockerlabs/blob/master/beginners/dockerfile/Writing-dockerfile.md
https://github.com/collabnix/dockerlabs/blob/master/beginners/dockerfile/ADD-command.md
https://docs.docker.com/engine/reference/builder/#expose
https://github.com/BretFisher/dockercon19
https://www.ctl.io/developers/blog/post/15-quick-docker-tips
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer
docker run -d –name mysql ctlc/mysql
docker run –link mysql:db ubuntu env

4. docker-compose :
https://docs.docker.com/compose/gettingstarted/

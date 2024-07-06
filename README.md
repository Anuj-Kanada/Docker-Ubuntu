# Docker


* Run the following command to uninstall all conflicting packages: </br>
  -for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do sudo apt-get remove $pkg; done

# Installation process
1. sudo apt update </br>
2. sudo apt install apt-transport-https ca-certificates curl software-properties-common (Above four packages is mandatory)</br>
3. curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add - (Add the GPG key for the official Docker repository to your system)</br>
4. sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable" (Add the Docker repository to APT sources. This will also update our package database with the Docker packages from the newly added repo.)</br>
5. sudo apt install docker-ce (install docker)</br>
6. sudo apt install -f (This is will fix package forcefully in case any error)</br>
7. docker --version (Check docker version) </br>
8. sudo systemctl status docker (Check docker status) </br>

# Post Installation steps:
-> By default, the docker command can only be run the root user or by a user in the docker group. Add system user to docker group, Please follow below steps :</br>
1. groups (Output will show users of docker group. ex : docker sudo www-data) </br>
2. sudo groupadd docker</br>
3. sudo usermod -aG docker $USER ($user refers username of system. sudo usermod -aG docker anuj_kanada. This command work for both system user who already logged in and also for who not logged in right now)</br>
4. newgrp</br>
-> If you run groups command again, Output will show users of docker group. ex : docker sudo www-data anuj_kanada   </br>
-> sudo docker ps and docker ps, If both command working it means you are on right path.</br>
-> docker ps (command to check active container)</br>

CONTAINER ID   IMAGE                                                    COMMAND                  CREATED       STATUS                 PORTS             </br>                                                                                                                                 NAMES
2d033d0259c7   ddev/ddev-webserver:v1.22.6-Training-built               "/pre-start.sh"          2 hours ago   Up 2 hours (healthy)   8025/tcp, 127.0.0.1:32791->80/tcp, 127.0.0.1:32790->443/tcp                                                                                        ddev-Training-web
ac29682c3468   ddev/ddev-dbserver-mariadb-10.4:v1.22.6-Training-built   "/docker-entrypoint.…"   2 hours ago   Up 2 hours (healthy)   127.0.0.1:32789->3306/tcp                                                                                                                          ddev-Training-db
d3e91b1faa1b   ddev/ddev-traefik-router:v1.22.6                         "/entrypoint.sh --co…"   3 hours ago   Up 3 hours (healthy)   127.0.0.1:80->80/tcp, 127.0.0.1:443->443/tcp, 127.0.0.1:8025-8026->8025-8026/tcp, 127.0.0.1:9200-9201->9200-9201/tcp, 127.0.0.1:10999->10999/tcp   ddev-router
e475a07ac980   elasticsearch:7.17.14                                    "/bin/tini -- /usr/l…"   3 hours ago   Up 3 hours (healthy)   9200/tcp, 9300/tcp                                                                                                                                 ddev-Training-elasticsearch
bb499f193eac   ddev/ddev-ssh-agent:v1.22.6-built                        "/entry.sh ssh-agent"    3 hours ago   Up 3 hours (healthy)






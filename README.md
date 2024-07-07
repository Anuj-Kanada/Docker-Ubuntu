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
-> docker ps -a (command to check both active and inactive containers)
</br>
-> docker ps -l (command to check latest container)</br>
->To remove a container : docker rm container_id
</br>
->To start a container : docker start container_id  </br>
->To stop a container : docker stop container_id       </br>
-> docker (command to check all options/arguments we can pass. ex : docker run hello-word )
</br>
->docker info (command to check about docker info like version, total container, running-pause containers etc)
</br>

#Configure Docker to start on boot

1. Enable Services:</br>
● sudo systemctl restart docker.service </br>
● sudo systemctl restart containerd.service




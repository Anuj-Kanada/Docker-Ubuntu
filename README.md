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
-> By default, the docker command can only be run the root user or by a user in the docker group. Add system user to docker group, Please follow below steps :







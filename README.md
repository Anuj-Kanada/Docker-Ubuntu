# Docker


* Run the following command to uninstall all conflicting packages: </br>
  -for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do sudo apt-get remove $pkg; done

# Installation process
1. sudo apt update </br>
2. sudo apt install apt-transport-https ca-certificates curl software-properties-common (Above four packages is mandatory)</br>
3. curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add - (Add the GPG key for the official Docker repository to your system)


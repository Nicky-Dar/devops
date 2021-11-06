# Docker Installation
You can install Docker Engine in different ways, depending on your needs:
Most users set up Docker’s repositories and install from them, for ease of installation and upgrade tasks. This is the recommended approach.
Some users download the DEB package and install it manually and manage upgrades completely manually. This is useful in situations such as installing Docker on air-gapped systems with no access to the internet.
## Install using the repository
Before you install Docker Engine for the first time on a new host machine, you need to set up the Docker repository. Afterward, you can install and update Docker from the repository.

### Set up the repository
Update the apt package index and install packages to allow apt to use a repository over HTTPS:
> sudo apt-get update

> sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
 
![image](https://user-images.githubusercontent.com/88620315/140605761-e44b593a-bc79-4470-bacd-9693a48ac9f9.png)

Add Docker’s official GPG key:
> curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

Use the following command to set up the stable repository. To add the nightly or test repository, add the word
> echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  (xenial) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

## Install Docker Engine
Update the apt package index, and install the latest version of Docker Engine and containerd, or go to the next step to install a specific version:
> sudo apt-get update 
> sudo apt-get install docker-ce docker-ce-cli containerd.io

![image](https://user-images.githubusercontent.com/88620315/140605774-5862e24e-6458-4aa3-b85e-029e692d5c18.png)
 

# docker hub Registration / Log in
## Registration 
Open https://hub.docker.com/
Sign up 
Fill the form

 
![image](https://user-images.githubusercontent.com/88620315/140605788-37f245b2-8261-46f8-84cd-722fc8d7ff90.png)

confirm the email verification 
choose your docker package
 
 
![image](https://user-images.githubusercontent.com/88620315/140605792-b65a4375-391a-43e6-a93e-63991706a280.png)

![image](https://user-images.githubusercontent.com/88620315/140605794-cd92c3c0-3cb5-4c5d-a713-0394424be19a.png)

## Log in
Open https://hub.docker.com/
Sign in
Fill the form
 
![image](https://user-images.githubusercontent.com/88620315/140605805-7a01c58a-9dc8-47e7-8b5b-cd754c94acd5.png)

 
![image](https://user-images.githubusercontent.com/88620315/140605809-58608906-9fbe-4de8-ba3d-456330e2b7e8.png)



# Installing Ansible on Ubuntu
To configure your machine and install Ansible run these commands:
```

$ sudo apt update
$ sudo apt install software-properties-common
$ sudo add-apt-repository --yes --update ppa:ansible/ansible
$ sudo apt install ansible
 
```
Buat file inventory
```
34.234.96.16 ansible_user=ubuntu
3.95.250.224 ansible_user=ubuntu
54.82.80.58 ansible_user=ubuntu
18.206.212.60 ansible_user=ubuntu
18.212.91.197 ansible_user=ubuntu
```
 
![image](https://user-images.githubusercontent.com/88620315/141708792-da96446d-9158-4575-8a3f-5e886e982321.png)

Copy key.pem ke dalam direktori yang sama dengan inventory

Jalankan ansible
`ansible all --key-file ssh.pem -i inventory -m ping `
 
![image](https://user-images.githubusercontent.com/88620315/141708802-7fe7d589-7416-4fea-adb2-bcd45074fd9f.png)

konfigurasikan ansible
> sudo nano ansible.cfg
 
![image](https://user-images.githubusercontent.com/88620315/141708821-b3dd7c76-2cb6-4a01-9002-e6b899fbde33.png)


### Buat file nginx.yml
sudo nano nginx.yml
```
---
- name: Setup Nginx
  hosts: 3.95.250.224
  become: true
  tasks:
    - name: Update system
      apt:
        update_cache: yes
    - name: Upgrade system
      apt:
        upgrade: dist

    - name: Install Nginx
      apt:
        name: nginx
        state: present
        update_cache: yes

```
jalankan nginx.yml
`ansible-playbook nginx.yml`
 
![image](https://user-images.githubusercontent.com/88620315/141708837-32c38085-945f-4d72-902e-5900458adb72.png)

![image](https://user-images.githubusercontent.com/88620315/141708844-1261a95c-b9a5-4de2-a459-e96927f3af4b.png)

 
### Buat file database.yml
sudo nano database.yml
```
---
- name: Setup Database
  hosts: 54.82.80.58
  become: true
  tasks:
    - name: Update system
      apt:
        update_cache: yes
    - name: Upgrade system
      apt:
        upgrade: dist

    - name: Install Mysql-Server
      apt:
        name: mysql-server
        state: latest
 
```
jalankan database.yml
`ansible-playbook database.yml`
 
![image](https://user-images.githubusercontent.com/88620315/141708863-5bf74b4a-d9e9-433f-b1a8-d08707c63897.png)

Buat file untuk instalasi docker di server


```
---
- name: Setup Docker & Docker Compose
  hosts: 
    - 34.234.96.16
    - 18.206.212.60 
    - 18.212.91.197 
  become: true
  tasks:
    - name: Update system
      apt:
        update_cache: yes

    - name: Upgrade system
      apt:
        upgrade: dist

    - name: Setup repository
      shell: "sudo apt-get install ca-certificates curl gnupg lsb-release"
      args:
        executable: /bin/bash

    - name: Add docker GPG key
      apt_key:
        url: https://download.docker.com/linux/ubuntu/gpg
        state: present

    - name: Add docker repository
      apt_repository:
        repo: deb https://download.docker.com/linux/ubuntu focal stable
        state: present

    - name: Update system
      apt:
        update_cache: yes

    - name: Install docker engine
      apt:
        name: "{{item}}"
        state: latest
        update_cache: yes
      loop:
        - docker-ce
        - docker-ce-cli
        - containerd.io

    - name: Install stable release docker compose
      shell: "sudo curl -L 'https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)' -o /usr/local/bin/docker-compose"
      args:
        executable: /bin/bash

    - name: Apply executable permission to the binary
      shell: "sudo chmod +x /usr/local/bin/docker-compose"
      args:
        executable: /bin/bash
```
 jalankan docker.yml
`ansible-playbook docker.yml`
 
![image](https://user-images.githubusercontent.com/88620315/141708871-34c6e80f-8ff1-455e-aafc-b6331821ea74.png)

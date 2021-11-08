# Jenkins
Jenkins adalah alat integrasi berkelanjutan open-source yang ditulis dalam Java. Ia menyediakan layanan integrasi kustom bagi pengembangan perangkat lunak. Ia merupakan sistem berbasis server yang digunakan oleh banyak tim pengembangan.

`sudo apt install default-jdk`
```
wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add –
sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
sudo apt update
sudo apt install jenkins
```
 
![image](https://user-images.githubusercontent.com/88620315/140700975-6a07fabf-3e48-4dc3-8d0e-0eeca4d53afb.png)

![image](https://user-images.githubusercontent.com/88620315/140700998-5521fc5a-a993-4f9d-b082-01550dc3136a.png)

 

Open browser http://34.192.169.116:8080
 
![image](https://user-images.githubusercontent.com/88620315/140701035-d9049cef-d5e4-4062-88a5-5f924b786dbb.png)

Input password yang terdapat pada /var/lib/jenkins/secrets/initialAdminPassword

Customize Jenkins plugins 
 
![image](https://user-images.githubusercontent.com/88620315/140701063-aae2016c-ecca-4459-8f5a-1bcd46336cd0.png)

Create admin user 

![image](https://user-images.githubusercontent.com/88620315/140701095-3e7908b3-cd83-438f-9985-223097431e82.png)

Set up Jenkins URL 
   
![image](https://user-images.githubusercontent.com/88620315/140701133-342ff7dd-e9df-4d35-8fb1-fbb5a835e7bc.png)

![image](https://user-images.githubusercontent.com/88620315/140701157-52e51e80-a01e-42d7-9469-4af99b5caaa9.png)

After done with the configuration, we can start using jenkins

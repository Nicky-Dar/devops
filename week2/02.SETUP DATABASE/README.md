# SETUP DATABASE

## A. Requirements
- Create new instance for Backend
- Install database on the server
- Can remote on the database from the client
- Setup security group with private IP

###
# Create new instance for Backend


![image](https://user-images.githubusercontent.com/88620315/139584162-c401ae7f-ba79-4c9d-beca-021eac81bd1f.png)
![image](https://user-images.githubusercontent.com/88620315/139584169-dbef7710-8b37-4d09-9d24-f6f2cd40defe.png)
![image](https://user-images.githubusercontent.com/88620315/139584176-d00ceeae-a2d5-4f46-a425-3fede8e55842.png)
![image](https://user-images.githubusercontent.com/88620315/139584191-dd60e491-565a-46d2-9fee-2310749394e5.png)
![image](https://user-images.githubusercontent.com/88620315/139584209-a6b23548-3737-4a46-b3a1-1aee0573b923.png)
![image](https://user-images.githubusercontent.com/88620315/139584232-53a241b4-67b1-421d-a1c7-dc147c67fba0.png)

# install database
>sudo apt install mysql-server

![image](https://user-images.githubusercontent.com/88620315/139584274-15d9da9b-7d4c-4b4c-a689-cb91f944183f.png)
>sudo mysql_secure_installation

Konfigurasikan validasi

Validasi : Y

Pilih level kekuatan validasi (0-2) 0: lemah 1: sedang 2: kuat 

Masukan password : 

.

.

.

![image](https://user-images.githubusercontent.com/88620315/139584356-9f163def-3f88-41cd-a4a8-bce09b777675.png)
>sudo mysql -u root -p

>[Password]

![image](https://user-images.githubusercontent.com/88620315/139584367-8cdf148e-ad50-4700-9f3c-bf6075501812.png)

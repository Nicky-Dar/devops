## A. Requirements
- Clone application in here https://github.com/sgnd/dumbplay-backend
- Change directory to **backend** and deploy the application.
- Import database with sequelize


#git clone

>git config --global user.name “Nicky-Dar”

>git config --global user.email “Nicholausnicky.nicky@gmail.com”

>git config –list

![image](https://user-images.githubusercontent.com/88620315/139599852-2e439fdb-5375-4d42-87e1-2889f3015db5.png)
![image](https://user-images.githubusercontent.com/88620315/139599856-833bc57e-4294-4662-af01-4865cab55851.png)

Install node js
Masuk ke directory backend
>npm install

Config file in config.json
>nano config.json

![image](https://user-images.githubusercontent.com/88620315/139599878-1e022679-6eda-42b4-a3e4-8c4b25dbbd9c.png)
> scp -r dumbplay.sql nicky@3.226.103.32:/home/nicky/

![image](https://user-images.githubusercontent.com/88620315/139599895-39efdd19-c2f3-4312-9a4a-501ae5b4813b.png)

![image](https://user-images.githubusercontent.com/88620315/139599901-b0019bb6-8815-43c5-9039-27344442dac5.png)

Install sequelize pada backend
>npm install --save-dev sequelize-cli -g

![image](https://user-images.githubusercontent.com/88620315/139599917-4e0893bc-11ea-4ac6-87a6-a08b21af1db5.png)

>sequelize db:migrate

![image](https://user-images.githubusercontent.com/88620315/139599928-32e93a1f-84e9-4508-bc48-7bcc83fb42e0.png)

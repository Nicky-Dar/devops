# AWS-Create-and-Setup-Server

Login into AWSeducate

![image](https://user-images.githubusercontent.com/88620315/138586868-91dddf93-7d66-486a-9af5-093be2a5d0b1.png)


Go to classroom

![image](https://user-images.githubusercontent.com/88620315/138586878-20381e76-f39b-4405-b4ea-bcb9cf741538.png)


Get in into AWS Console and choose Launch a virtual machine

![image](https://user-images.githubusercontent.com/88620315/138586880-ba6bda25-00ba-4144-a9e6-80b2409b1ee9.png)

EC2

![image](https://user-images.githubusercontent.com/88620315/138586881-9b1367c5-95bc-40cd-b1c0-dd4248d53bfb.png)

Launch instance and search the oprating system for the server

![image](https://user-images.githubusercontent.com/88620315/138586889-d46b576f-bb30-4ad5-a51e-4fcad2f49621.png)

Choose the Instance type

![image](https://user-images.githubusercontent.com/88620315/138587009-7d56ff3d-865d-4bc1-a8b0-71808442f5d0.png)



Configure the Instance detail

![image](https://user-images.githubusercontent.com/88620315/138587012-f08d7989-5353-4682-91aa-2013c4f24bce.png)


Add storage 

![image](https://user-images.githubusercontent.com/88620315/138587015-75ba404d-f218-465f-ba1c-b007191b7fb2.png)


Configure security group

![image](https://user-images.githubusercontent.com/88620315/138587019-d6e49a40-0ed7-4d59-80c3-6c1f4aefe7f9.png)

review instance Launch

![image](https://user-images.githubusercontent.com/88620315/138587027-b2d961bb-ebe7-4127-8aa8-5058e3d4fc20.png)

next we can launch the instance.

Create new keypair and download it

![image](https://user-images.githubusercontent.com/88620315/138587099-dd5e6e4c-3e45-4454-855d-bc6b8b75cc24.png)

Save the key pair!

The launch status is :

![image](https://user-images.githubusercontent.com/88620315/138587106-4870ef58-0196-43fc-b2c5-5cf7fa4914bf.png)


For set the IP address go to menu **Elastic IPs** 

![image](https://user-images.githubusercontent.com/88620315/138587145-8d2bd0ba-8951-4ecc-80e8-ad9cdf28496e.png)


Allocate Elastic IP address

![image](https://user-images.githubusercontent.com/88620315/138587154-8817208f-e0c3-40bd-9c72-d763723e0efc.png)
![image](https://user-images.githubusercontent.com/88620315/138587167-65777ad0-04c7-427f-86eb-53e7ef6710bf.png)


Associate Elastic IP address

![image](https://user-images.githubusercontent.com/88620315/138587181-691c6f02-a678-4926-916c-2cdfde7427bd.png)

Choose where is the instance want to connect with the IP 

![image](https://user-images.githubusercontent.com/88620315/138587183-61b582bd-9e6c-4bbb-ba7d-8143ffb1d9cd.png)


with terminal create folder/ directory to save all change

Save key pair at that directory too.

>chmod 400 [key.pem]

![image](https://user-images.githubusercontent.com/88620315/138587278-16662d2c-5978-4a93-b061-05bea6bf9c4f.png)

Remote:

>ssh -I [key.pem] [user(default: ubuntu)]@[IP]

![image](https://user-images.githubusercontent.com/88620315/138587294-75caa3ff-2cf0-4f1a-b527-428ebf1838df.png)

## Create docker image for front-end
Login into docker
>docker login 

![image](https://user-images.githubusercontent.com/88620315/140635270-be185657-5413-41f3-ad9d-750dc68b4f47.png)

### Nginx
Pull nginx
> docker pull nginx

![image](https://user-images.githubusercontent.com/88620315/140635281-ca43347d-1198-4d9e-a3b4-2ab56b16684b.png)

Run nginx 
> docker run --name webserver -p 8080:80 nginx

![image](https://user-images.githubusercontent.com/88620315/140635294-d4122ffd-9394-4ddc-95a4-fa0095b2b91f.png)

Or

>docker run --name webserver -p 8080:80 -d nginx

![image](https://user-images.githubusercontent.com/88620315/140635304-42a5c8d6-bd2c-402e-a69c-d8aa74933084.png)

![image](https://user-images.githubusercontent.com/88620315/140635309-fb645d4f-9409-4d17-825f-82985def62a0.png)

Docker create
> docker container create –name [nama] -p [new port]:[port] image
 
![image](https://user-images.githubusercontent.com/88620315/140635390-41e641ff-4a6a-461d-b537-546ac47e79f0.png)

docker start nginxfront
 
![image](https://user-images.githubusercontent.com/88620315/140635412-9ede27c3-645f-4989-b640-d9820bda69af.png)

Create dockerfile
 
![image](https://user-images.githubusercontent.com/88620315/140635485-f93497b2-dc79-477e-a78d-a92fd06136af.png)

### Node
docker pull node
 
![image](https://user-images.githubusercontent.com/88620315/140635493-9da5bbe7-159f-47ee-ad21-441a0ee755fa.png)

Build:
>docker build -t nickydar/frontend:1.0 .
 
![image](https://user-images.githubusercontent.com/88620315/140635512-c322dfa8-b495-4801-85f7-49cc09f7a02c.png)
![image](https://user-images.githubusercontent.com/88620315/140635519-c09ac978-7763-4439-a43b-11de0e0c2874.png)

 
Push
docker push nickydar/frontend
 
![image](https://user-images.githubusercontent.com/88620315/140635584-e601e380-2623-4e59-909e-9b66bd69ac95.png)
![image](https://user-images.githubusercontent.com/88620315/140635610-7d3c0ea2-7e23-4b55-a9bc-dbabdabc7975.png)

 
## Backend
Docker pull node

![image](https://user-images.githubusercontent.com/88620315/140635701-85fa4f4f-83c2-4e1d-a2e0-5df03d983b94.png)

docker pull nginx

![image](https://user-images.githubusercontent.com/88620315/140635708-d485ddea-df07-4f44-a4d9-c2e5d5534560.png)

Create Dockerfile
 
![image](https://user-images.githubusercontent.com/88620315/140635715-178d49e5-eaab-4ef8-b10f-7db5b3a06a17.png)

docker build -t nickydar/backtend:1.0 .

![image](https://user-images.githubusercontent.com/88620315/140635717-b0eeffd3-c5f3-4db3-a318-85764c29f895.png)

  docker push nickydar/backend:1.0
 
![image](https://user-images.githubusercontent.com/88620315/140635720-0f911afc-4e3e-47e8-8117-86c79116d47c.png)

![image](https://user-images.githubusercontent.com/88620315/140635746-1166fcca-60c5-4f82-9539-ab297f3fe3d9.png)

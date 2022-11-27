## lunch ec2(slave_4) ubuntu
![image](https://user-images.githubusercontent.com/40553867/204118619-0774c752-8f1e-4725-a902-ffe6f8601206.png)

![image](https://user-images.githubusercontent.com/40553867/204118636-56b33eba-2f9e-4eed-aade-ba9d9f822e85.png)

![image](https://user-images.githubusercontent.com/40553867/204118640-77778f20-62f8-4d06-997c-e9197661dfd0.png)

![image](https://user-images.githubusercontent.com/40553867/204118643-27b6f4e4-1882-4668-a1a9-1e874c7a42de.png)

![image](https://user-images.githubusercontent.com/40553867/204118647-dbc74665-84dd-4015-bc62-2d90404a4efc.png)

![image](https://user-images.githubusercontent.com/40553867/204119124-2cf5de11-efc5-4025-b61f-f32bd3999572.png)

![image](https://user-images.githubusercontent.com/40553867/204119162-5257c403-2ebc-4bcf-8e24-1398016ac947.png)

### connect ec2 instance with ssh

![image](https://user-images.githubusercontent.com/40553867/204119209-1af9bfb4-6799-455b-9886-2b80d12d31e4.png)

![image](https://user-images.githubusercontent.com/40553867/204119224-48670dd2-6bc1-45fa-855f-509893fab04f.png)

```
sudo apt install nginx -y
```
![image](https://user-images.githubusercontent.com/40553867/204119244-32b2fce0-c847-403f-b6b2-91f7de978d14.png)

![image](https://user-images.githubusercontent.com/40553867/204119276-236c2921-0d05-41a3-bc90-8f1edcd5bd03.png)

## add website 
![image](https://user-images.githubusercontent.com/40553867/204119350-8b56ee18-eb3a-4bc7-acac-8f978c00924a.png)

## install nodejs
```
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash - &&\
sudo apt-get install -y nodejs
```

```
npm install
npm run build
```

### copy build content to /var/www/html/
```
sudo cp -r build/* /var/www/html/
```

![image](https://user-images.githubusercontent.com/40553867/204119840-9012a6e3-15b9-4a81-8dda-862270c20c2c.png)

![image](https://user-images.githubusercontent.com/40553867/204119989-bfab7bb4-177b-4e87-9dfd-759a65791034.png)

## add site to sites-available 

```
cd /etc/nginx/sites-available
cp default krishnn.ml
vi krishnn.ml
```

```
 server_name krishnn.ml  www.krishnn.ml;
```

![image](https://user-images.githubusercontent.com/40553867/204121049-5e81dfc3-6ceb-404f-95bc-7a7188b133a3.png)

![image](https://user-images.githubusercontent.com/40553867/204121061-52897b8e-0b9c-40cd-80d7-8269e8c9e091.png)

```
ln -s /etc/nginx/sites-available/krishnn.ml /etc/nginx/sites-enabled/
```

![image](https://user-images.githubusercontent.com/40553867/204121124-99862ed4-7646-4413-8863-5b376e67eb95.png)

```
systemctl restart nginx
```
![image](https://user-images.githubusercontent.com/40553867/204121151-4be9d2cb-a774-4c14-8269-f2c350e35eae.png)

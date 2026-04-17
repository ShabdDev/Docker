### Tasks To Be Performed:
1. Launch the Apache2 container created in previous module
2. Create a Docker volume on /var/www/html

### Solution
```
1. Stop and Remove Old Container (if running)

sudo docker stop apache_custom_container  
sudo docker rm apache_custom_container  

2. Create Docker Volume

sudo docker volume create myvolume  

3. Run New Container with Volume

sudo docker run -d -p 80:80 --name apache_volume_container -v myvolume:/var/www/html apache-custom:v1  

4. Access Container

sudo docker exec -it apache_volume_container bash  

5. Create HTML File inside Volume

echo "<h1>Volume Working </h1>" > /var/www/html/index.html  

### 6. Verify in Browser

http://<EC2-PUBLIC-IP>

```
### Expected Output

Custom page should display:

<h1>Volume Working </h1>


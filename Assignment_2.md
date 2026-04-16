### Tasks To Be Performed:
1. Save the image created in assignment 1 as a Docker image
2. Launch container from this new image and map the port to 81
3. Go inside the container and start the Apache2 service
4. Check if you are able to access it on the browser

### Solution
```bash
 1. Check existing container
sudo docker ps -a

 2. Create image from container
sudo docker commit myubuntu myapache:v1

 3. Verify image
sudo docker images

 4. Run container on port 81
sudo docker run -dit -p 81:80 --name myapache_container myapache:v1

 5. Access container
sudo docker exec -it myapache_container bash

 6. Start Apache
service apache2 start

 7. Test in browser
http://<EC2-PUBLIC-IP>:81
```

### Tasks To Be Performed:
1. Use the saved image in the previous assignment
2. Upload this image on Docker Hub
3. On a separate machine pull this Docker Hub image and launch it on port 80
4. Start the Apache2 service
5. Verify if you are able to see the Apache2 service

### Solution
```bash
1. Login to Docker Hub
sudo docker login

2. Tag Image
sudo docker tag myapache:v1 <username>/myapache:v1

3. Push Image
sudo docker push <username>/myapache:v1

```

### On Second Machine
```bash
4. Install Docker
sudo apt update
sudo apt install docker.io -y

5. Pull Image
sudo docker pull <username>/myapache:v1

6. Run Container
sudo docker run -dit -p 80:80 --name apache_from_hub <username>/myapache:v1

7. Enter Container
sudo docker exec -it apache_from_hub bash

8. Start Apache
service apache2 start

9. Test
http://<EC2-PUBLIC-IP>
```

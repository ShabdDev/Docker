### Tasks To Be Performed:
1. Pull Ubuntu container
2. Run this container and map port 80 on the local
3. Install Apache2 on this container
4. Check if you are able to access the Apache page on your browser

### Solution 
```bash
# STEP 1: Update system
sudo apt update

# STEP 2: Install Docker
sudo apt install docker.io -y

# STEP 3: Pull Ubuntu image
docker pull ubuntu

# STEP 4: Run container with port mapping
docker run -dit -p 80:80 --name myubuntu ubuntu

# STEP 5: Enter container
docker exec -it myubuntu bash

# STEP 6: Inside container → update packages
apt update

# STEP 7: Install Apache2
apt install apache2 -y

# STEP 8: Start Apache
service apache2 start

# STEP 9: Check Apache status (optional)
service apache2 status

# STEP 10: Exit container
exit

# STEP 11: Verify container is running
docker ps

```

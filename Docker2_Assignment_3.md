### Tasks To Be Performed:
1. Create 5 custom container with 5 different default pages
2. Using Docker Compose deploy these 5 containers on port 81, 82, 83, 84
and 85 respectively

### Solution
```
1. Create folders
mkdir compose-apache
cd compose-apache
mkdir site1 site2 site3 site4 site5

2. Create HTML files
nano site1/index.html
<h1>Site 1 (Port 81)</h1>

nano site2/index.html
<h1>Site 2 (Port 82)</h1>

nano site3/index.html
<h1>Site 3 (Port 83)</h1>

nano site4/index.html
<h1>Site 4 (Port 84)</h1>

nano site5/index.html
<h1>Site 5 (Port 85)</h1>

3. Create docker-compose.yml
nano docker-compose.yml

version: '3'

services:
  site1:
    image: apache-custom:v1
    container_name: site1_container
    ports:
      - "81:80"
    volumes:
      - ./site1:/var/www/html

  site2:
    image: apache-custom:v1
    container_name: site2_container
    ports:
      - "82:80"
    volumes:
      - ./site2:/var/www/html

  site3:
    image: apache-custom:v1
    container_name: site3_container
    ports:
      - "83:80"
    volumes:
      - ./site3:/var/www/html

  site4:
    image: apache-custom:v1
    container_name: site4_container
    ports:
      - "84:80"
    volumes:
      - ./site4:/var/www/html

  site5:
    image: apache-custom:v1
    container_name: site5_container
    ports:
      - "85:80"
    volumes:
      - ./site5:/var/www/html

4. Run containers
sudo docker-compose up -d
```
### Access
```
- http://<EC2-IP>:81  
- http://<EC2-IP>:82  
- http://<EC2-IP>:83  
- http://<EC2-IP>:84  
- http://<EC2-IP>:85  
```

### Tasks To Be Performed:
1. Create a Dockerfile with the following specs:
- Ubuntu container
- Apache2 installed
- Apache2 should automatically run once the container starts
2. Submit the Dockerfile for assignment completion

### Solution

 *Dockerfile*
```bash
FROM ubuntu
RUN apt update
RUN apt install apache2 -y
ENTRYPOINT ["apachectl", "-D", "FOREGROUND"]
```
### Steps Performed
```bash
1. Create Directory
mkdir docker-apache
cd docker-apache

2. Create Dockerfile
nano Dockerfile

3. Build Image
sudo docker build -t apache-auto:v1 .

4. Run Container
sudo docker run -d -p 80:80 --name apache_auto_container apache-auto:v1

5. Test
http://<EC2-PUBLIC-IP>
```
   

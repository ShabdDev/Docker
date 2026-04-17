### Tasks To Be Performed:
1. Create a sample HTML file
2. Use the Dockerfile from the previous task
3. Replace this sample HTML file inside the Docker container with the default
page

### Solution
*Dockerfile*
```bash
FROM ubuntu
RUN apt update && apt install apache2 -y
COPY index.html /var/www/html/index.html
ENTRYPOINT ["apachectl", "-D", "FOREGROUND"]
```
### Steps
```
1. Create HTML file
nano index.html

2. Build Image
sudo docker build -t apache-custom:v1 .

3. Run Container
sudo docker run -d -p 80:80 --name apache_custom_container apache-custom:v1

4. Test
http://<EC2-PUBLIC-IP>
```

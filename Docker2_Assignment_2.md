### Tasks To Be Performed:
1. Use the Apache2 container created in previous module
2. Create a bind mount on /var/www/html to replace html files dynamically

### Solution
```dash
1. Create HTML file
mkdir website
cd website
nano index.html

2. Add content
<h1>Dynamic Page 🚀</h1>

3. Run container with bind mount
sudo docker run -d -p 80:80 --name apache_bind_container -v $(pwd):/var/www/html apache-custom:v1

4. Test
http://<EC2-PUBLIC-IP>

```
### Dynamic Update

Edit file:
nano index.html

Refresh browser → changes visible instantly

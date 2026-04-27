# DOC-LAB-4-Docker-Installation-and-Web-Server-Setup

# Step 1: Update system
```bash
sudo yum update -y
```
# Step 2: Install Docker
```bash
sudo yum install docker -y
```
# Step 3: Start Docker service
```bash
sudo systemctl start docker
```
# Step 4: Enable Docker (auto start after reboot)
```bash
sudo systemctl enable docker
```
# Step 5: Give permission to ec2-user (optional, avoids sudo every time)
```bash
sudo usermod -aG docker ec2-user
```

# Logout and login again after this step

# Step 6: Check Docker version
```bash
docker --version
```
# Step 7: Pull image (Nginx or HTTPD)
```bash
docker pull nginx
```
# OR
```bash
docker pull httpd
```
# Step 8: Check images
```bash
docker images
```
# Step 9: Run container
```bash
docker run -d -p 1000:80 nginx
```
# OR
```bash
docker run -d -p 1000:80 httpd
```
# Step 10: Check running containers
```bash
docker ps
```

# Quick understanding

Port mapping -p 1000:80 means:

1000 = your EC2 port (browser access)
80 = container port (web server inside Docker)

So you can open in browser:

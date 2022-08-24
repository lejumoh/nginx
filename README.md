# nginx
##update your OS
sudo yum update -y

##Install dependencies
sudo amazon-linux-extras install docker

### Install Docker
sudo yum install docker

### Start Docker Service
sudo service docker start

### Give docker permissions
sudo usermod -a -G docker ec2-user

### Get information of docker installed
docker info

### Build your docker image
docker build -t webserver .

### Run a container using the image built
docker run -it --rm -d -p 8080:80 --name web webserver

### Check your installation of nginx web server (please whitelist port 80 on your security group)
Open your browser and navigate to http://localhost:8080 to make sure our html page is being served correctly.

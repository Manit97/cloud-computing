# Cloud Computing and AWS
## Setting up an EC2 instance and begin the node application
- Follow steps on AWS to create an instance
- sudo chmod 400 devop_bootcamp.pem in your .ssh folder to ensure your key is not publicly viewable.
- Copy the app folder to your EC2 by using 'sudo scp -i ~/.ssh/devop_bootcamp.pem -r app/ ubuntu@ec2-54-78-10-214.eu-west-1.compute.amazonaws.com:/home/ubuntu/' (IP Changes)
- sudo ssh -i "devop_bootcamp.pem" ubuntu@ec2-54-78-10-214.eu-west-1.compute.amazonaws.com to get into ubuntu
- Make Provision.sh 
- #!/bin/bash

sudo apt-get update -y 
sudo apt-get upgrade -y
sudo apt-get install nginx -y
sudo systemctl enable nginx
sudo apt-get install nodejs -y 
sudo apt-get install python-software-properties 
curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
sudo apt-get install nodejs -y
sudo npm install pm2 -g
cd app
npm install

-to reverse proxy you must change your default file in /etc/nginx/sites-available/default

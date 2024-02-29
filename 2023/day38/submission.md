### Task1:

Create an IAM user with username of your own wish and grant EC2 Access. Launch your Linux instance through the IAM user that you created now and install jenkins and docker on your machine via single Shell Script.

### Task2:

In this task you need to prepare a devops team of avengers. Create 3 IAM users of avengers and assign them in devops groups with IAM policy.

A)
iam >>user create user >> give access and set passwor dand set account alias in  dashboard of root account and add account alias so it looks like console.
https://alias.signin.aws.amazon.com/console

docker-jenkins-install.sh//////////////////////////////////////////////////
#!/bin/bash
sudo apt-get update -y
# install docker
sudo apt install -y apt-transport-https ca-certificates curl software-properties-common

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update -y
apt-cache policy docker-ce
sudo apt install docker-ce -y
sudo usermod -aG docker $USER

# install jenkins

sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update -y
sudo apt-get install jenkins -y
////////////////////////////////////////////////////////////////////////


create new user group "avengers" add iam full access policy to it
create users spiderman, ironman, hulk add them to it

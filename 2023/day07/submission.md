## Tasks

1.  You have to install docker and jenkins in your system from your terminal using package managers
A)  sudo apt-get update
    sudo apt-get install docker.io
    download java jre
    wget jenkins url 
    sudo apt-get install jenkins

2.  Write a small blog or article to install these tools using package managers on Ubuntu and CentOS
A)  download java for jenkins and run sudo apt-get update to install all the files and apt-get upgrade to upgrade versions then wget the jenkins and install it similarly do for docker

## Tasks

1.  check the status of docker service in your system (make sure you completed above tasks, else docker won't be installed)
A)  sudo systemctl status docker  &&  sudo systemctl status jenkins


2.  stop the service jenkins and post before and after screenshots
A)  sudo systemctl stop jenkins

3.  read about the commands systemctl vs service
A)  systemctl uses systemD which is latest version and usessystemD process to check the satus and run command where as serivce uses sysvint where it runs init script ot start stopp and for other commands
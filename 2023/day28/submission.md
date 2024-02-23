# Pre-requisites

Let’s say we’re starting with a fresh Ubuntu 22.04 Linux installation. To get an agent working make sure you install Java ( same version as jenkins master server ) and Docker on it.

`Note:-
While creating an agent, be sure to separate rights, permissions, and ownership for jenkins users. `

# Task-01

- Create an agent by setting up a node on Jenkins

- Create a new AWS EC2 Instance and connect it to master(Where Jenkins is installed)

- The connection of master and agent requires SSH and the public-private key pair exchange.
- Verify its status under "Nodes" section.

- You can follow [this article](https://www.linkedin.com/posts/chetanrakhra_devops-project-share-activity-7017885886461698048-os5f?utm_source=share&utm_medium=member_android) for the same

A)
ssh-keygen in master
add the public key of master to authorised keys of slave
install java in slave
add the private key of master to the credentails of jenkins and add host deatils etc in node creation

# Task-02

- Run your previous Jobs (which you built on Day 26, and Day 27) on the new agent

- Use labels for the agent, your master server should trigger builds for the agent server.

A)
add usermod permissions then restart instance and change the node host address as it is changed
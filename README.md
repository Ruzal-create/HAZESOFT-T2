# HAZESOFT-T2
## _USING ANSIBLE TO DEPLOY DOCKERFILE_
## Prerequisites

- Have a ubuntu server/remote machine. 
- Have an access to the ssh key for connection.



## Understanding Ansible playbook

This Ansible playbook automates the process of copying the dockerfile and other necessary files in the host machine. 
The playbook consists of several **tasks** 

**Task 1**: update package manager task
**Task 2**: Install docker dependencies
**Task 3**: Add Docker GPG key
**Task 4**: Add Docker repository
**Task 5**: Update package manager cache again
**Task 6**: Install Docker 
**Task 7**: Clone the repository
**Task 8**: Copy Dockerfile to remote instance
**Task 9**: Copy nginx config file to remote instance
**Task 10**: Build Docker image
**Task 11**: Start Docker container

Run asnible playbook by running the following command:
```sh
ansible-playbook -i inventory.ini deploy.yml --private-key=<your_keyfile_name>
```
_Note: inventory.ini file consists web hosts_
![Screenshot](image3.jpg)

Now connect to the remote machine through **ssh**
```sh
ssh -i "<your_pem_file>" ubuntu@<ip_address>
```
![Screenshot](image.jpg)

After successfully connecting to your remote machine run the curl command
```
http://localhost:9000/site/index.html
```
![Screenshot](image2.jpg)











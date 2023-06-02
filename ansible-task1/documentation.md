## INSTALL NGINX,DOTNET,JAVA THROUGH ANSIBLE CONTROL NODE
---

###step to perform
 1. Creat two ubuntu vm's
 2. Enable  the passwd authentication
 ```
 sudo vi /etc/ssh/sshd_config
```	
![alt text](./images/image1.png)
3. Restart the sshd service
![alt text](./images/image2.png)
4. now create a user "devops"on both the instance
![alt text](./images/image3.png)
5. Give sudo permissions to the users onthe both the instances
![alt text](./images/image5.png)
6. Now login to the  devops user on both the instance
![alt text](./images/image6.png)
7. Now create ssh-keygen on controii node
![alt text](./images/image7.png)
8. Now copy id of the control node  to the
 node1 by giving the private ip adress of node1
![alt text](./images/image8.png)
 ###NOW WE HAVE CONNECTED BOTH THE MACHINES
 
 9. To check the create a hosts file with node1 private ip adresses and run the command 
 ```![alt text](./images/image9.png)

 ansible -i hosts -m ping 
 ```
  it will give some output which looks like this below 

  ### NOW INSTALL ANSIBLE IN CONTROL NODE IN DEVOPS

  ```
  sudo apt update
sudo apt install software-properties-common -y
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install ansible -y
```
![alt text](./images/image11.png)
### INSTALLING JAVA USING ANSIBLE 

1. Create two directories named as inventory playbooks 
2. in inventory create hosts file and give node1 private ip adress
![alt text](./images/image12.png)
3. in the playbooks directory write a play installing java
![alt text](./images/image13.png) 
4. Now run the command 
```
![alt text](./images/image14.png)
ansible-playbook -i <inventory_path> <playbooks_path>
```
### NOW WE WILL SEE OUTPUT LIKE THIS 
### INSTALLING DOTNET AND NGINX
![alt text](./images/WhatsApp%20Image%202023-06-02%20at%201.52.38%20PM%20(1).jpeg)
1. in the playbooks directory write a play installing nginx and dotnet
![alt text](./images/WhatsApp%20Image%202023-06-02%20at%201.52.38%20PM.jpeg)

 

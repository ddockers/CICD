# Infrastructure as Code (IaC)

## What is IaC?
Managing computer data centres using configuration tools, rather than with physical hardware.

The xonfiguration files contain the infrastructure specifications, so it's easier to edit and distribuse configurations.

## Ansible
- Ansible is a configuration management tool.
- Ansible is cloud independant. You can orchestrate the entire application environment no matter where it’s deployed.
- Ansible is agent-less. An Ansible controller can be created what can communicate with nodes that don't need to have Ansible installed.

![Ansible architecture](https://i.imgur.com/tzLV6y4.png)

## IaC with Ansible
1. Launch three EC2 instances
   
2. Label the instances - *controller*, *web-app* and *db*
   
3. `ssh` into each of the instances and update and upgrade to check that they can accept requests
   
4. In the controller, install dependencies
```
sudo apt-get install software-properties-common
```

5. Ansible then needs to be installed. One of Ansible's dependencies is Python. This does not need to be installed separately since Ubuntu already has Python installed
   1. Clone ansible from the ansible repo
   ```
   sudo apt-add-repository ppa:ansible/ansible
   ```
   2. Run update `sudo apt update -y`
   3. Install ansible
   ```
   sudo apt install ansible -y
   ```
   4. Make sure it's installed
   ```
   ansible --version
   ```
6. Navigate to Ansible folder. This is where the playbook is
```
cd /etc/ansible
```
7. the ssh pem file needs to be added to this folder. Navigate to `~/.ssh`. The easiest way is to run `sudo nano tech241.pem` and paste in the key.
8. Change permissions to read only
```
chmod 400 tech241.pem
```

9. Make sure we can ssh into an agent node from the controller. **Use the `sudo` command**, then paste the path directly (without the need to add `~/.ssh/`).

![ssh into agent node](https://i.imgur.com/aNp2Mfk.png)

Do this for both nodes (web app and db).

10.  If this all works, navigate to the default ansible directory.
```
cd /etc/ansible
```
Use `ls` to make sure the `hosts` file is there.

11.  Install tree package
```
sudo apt install tree -y
```
Run `tree` to make sure it's installed.

![Tree](https://i.imgur.com/dDOCKSO.png)


12. We need to be able to communicate with the nodes. We can do this by adding the path in the `host` file. Run `sudo nano hosts` and enter the following command:
```
[web]
ec2-instance ansible_host=34.241.184.76 ansible_user=ubuntu ansible_ssh_private_key_file=~/.ssh/tech241.pem
```

We've created a group, rather than an individual IP. 
We're using an EC2 instance, and the host of that instance is the IP address of the node (web app, in this case).
The user is Ubuntu, and the private key file can be found in the path at the end. Add the same command for the db (sing the db's IP address)

![nano web and db](https://i.imgur.com/8A3Mp5J.png)

1.  Ping.
```
sudo ansible web -m ping
```
```
sudo ansible db -m ping
```

I should get a pong in return...
![Ping Pong](https://i.imgur.com/VrGmsAs.png)

To ping all nodes, use `sudo ansible all -m ping`.

## Ansible Playbook

Web VM IP: 34.244.45.248

DB VM IP: 3.253.143.243

### Hosts file code
```
[web]
ec2-instance ansible_host=34.244.45.248 ansible_user=ubuntu ansible_ssh_private_key_file=~/.ssh/tech241.pem
[db]
ec2-instance ansible_host=3.253.143.243 ansible_user=ubuntu ansible_ssh_private_key_file=~/.ssh/tech241.pem
```
### Playbook
```
# YAML files start with --- 3 dashes
# Create a playbook to install nginx in web node

# which host to perform the task
---
- hosts: web
# see the logs by gathering facts
  gather_facts: yes
# admin access
  become: true
# add the instrutions - install nginx in web
  tasks:
    - name: Installing nginx
      apt: pkg=nginx state=present
# make sure status of nginx is actively running

# ad hoc command to check the status
```

Nginx is running on DB VM, not app VM.
# Project1
Azure Cloud Network
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

Azure Cloud Network Diagram ![Network Diagram](https://user-images.githubusercontent.com/83511424/132109856-1d235367-92d9-4a12-b29d-e110455e9997.png)



These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the file may be used to install only certain pieces of it, such as Filebeat.

All playbook and configuration files can be foung in ~/Project1/Ansible

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly efficient and responsive to users, in addition to restricting bad traffic to the network.
Load balancers protect your system from DDOS attacks by only allowing good traffic through. The advantage of a jump box is it allows you to connect to your system in a secure manner while being monitored.
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the file system and system metrics.
Filebeat collects log files on the system. Metricbeat records machine metrics.
The configuration details of each machine may be found below.

| Name     | Function | IP Address                                  | Operating System |
|----------|----------|---------------------------------------------|------------------|
| Jump Box | Gateway  | 10.0.0.5 (Private)/40.121.153.30 (Public)   | Linux            |
| Elk VM   | Server   | 172.16.5.4 (Private)                        | Linux            |
| Web-1    | Server   | 10.0.0.9 (Private)/20.85.210.174 (Public)   | Linux            |
| Web-2    | Server   | 10.0.0.4 (Private)/20.85.210.174 (Public)   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the virtual machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
10.0.0.9/10.0.0.4/172.16.5.4

Machines within the network can only be accessed by the jumpbox.
Jump Box 10.0.0.5

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses       |
|----------|---------------------|----------------------------|
| Jump Box |        Yes          |     My home IP address     |
| ELK VM   |        No           |     My home IP address     |
| Web-1    |        No           |     10.0.0.5               |
| Web-2    |        No           |     10.0.0.5               |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
The advantage of automating configuration with Ansible is that you can configure multiple servers from that playbook.

The playbook implements the following tasks:
- Install docker.io
- Install pip3
- Install docker python module
- Download and launch a docker web container
- Enable docker services

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![docker ps - Copy](https://user-images.githubusercontent.com/83511424/131423448-7270a30b-2ab7-4d35-8b60-597cbf89c9d4.PNG)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
10.0.0.9/10.0.0.4

We have installed the following Beats on these machines:
Filebeat and Metricbeat

These Beats allow us to collect the following information from each machine:

Filebeat collects log events, which we use to track and monitor user log messages. 

Metricbeat collects metric data, which we use to track system health and metrics.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the configuration file to /etc/ansible.
- Update the hosts file to include all private IP addresses of the machines you wish install and configure ELK in.
- Run the playbook, and navigate to Kibana (Public_ELK_IP:5601) to check that the installation worked as expected.

- Which file is the playbook? Where do you copy it? The playbook is elk.yml and it should be copied to /etc/ansible.
- Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on? /etc/ansible/hosts
- Which URL do you navigate to in order to check that the ELK server is running? http://[your.VM.IP]:5601/app/kibana

As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc.

-ssh sysadmin@JumpBox IP address

-sudo docker start container (conatiner name)

-sudo docker attach container (container name)

-ansible-playbook elk.yml

-(http://your.VM.IP:5601/app/kibana#/home)

# Project1
Project 1
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

Azure Cloud Network Diagram [Network Diagram](https://user-images.githubusercontent.com/83511424/132070778-4a376fdc-8982-4bde-90d8-e19c51755a3a.png)



These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the file may be used to install only certain pieces of it, such as Filebeat.

All playbook and configuration files can be foung in ~/Project1/Ansible

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly efficient and responsive to users, in addition to restricting bad traffic to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_
Load balancers protect your system from DDOS attacks by only allowing good traffic through. The advantage of a jump box is it allows you to connect to your system in a secure manner while being monitored.
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the file system and system metrics.
- _TODO: What does Filebeat watch for?_
- _TODO: What does Metricbeat record?_
Filebeat collects log files on the system. Metricbeat records machine metrics.
The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address                                  | Operating System |
|----------|----------|---------------------------------------------|------------------|
| Jump Box | Gateway  | 10.0.0.5 (Private)/40.121.153.30 (Public)   | Linux            |
| Elk VM   | Server   | 172.16.5.4 (Private)                        | Linux            |
| Web-1    | Server   | 10.0.0.9 (Private)/20.85.210.174 (Public)   | Linux            |
| Web-2    | Server   | 10.0.0.4 (Private)/20.85.210.174 (Public)   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the virtual machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses
10.0.0.9 10.0.0.4 172.16.5.4
Machines within the network can only be accessed by the jumpbox.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?
Jump Box 10.0.0.5

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box |        Yes          |     76.97.16.108     |
| ELK VM   |        Yes          |     76.97.16.108     |
| Web-1    |        Yes          |         Any          |
| Web-2    |        Yes          |         Any          |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_
The advantage of automating configuration with Ansible is that you can configure multiple servers from that playbook.
The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- Install docker.io
- Install pip3
- Install docker python module
- Download and launch a docker web container
- Enable docker services

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![docker ps - Copy](https://user-images.githubusercontent.com/83511424/131423448-7270a30b-2ab7-4d35-8b60-597cbf89c9d4.PNG)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_ 10.0.0.9 10.0.0.4

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_ Filebeat and Metricbeat

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._

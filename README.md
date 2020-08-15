# ELK-Stack_Project
Details on depolyment of ELK-Stack
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

https://github.com/Dru-Ha/ELK-Stack_Project/pull/1

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the ansible-playbook file may be used to install only certain pieces of it, such as Filebeat.

  This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting access to the network.
- Load balancers protect the availability of a network.  

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the files and system logs.
- Filebeat watches for changes to files and logs.
- Metricbeat records system status metrics.  

The configuration details of each machine may be found below.


| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.1   | Linux            |
|Elk-Server|Elk Server| 10.1.0.4   | Linux            |
| Web-1    |  Server  | 10.0.0.5   | Linux            |
| Web-2    |  Server  | 10.0.0.6   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 52.249.176.202

Machines within the network can only be accessed by ssh.
- Remote user machine IP 52.249.176.202

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | 10.0.0.1 10.0.0.2    |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- Automatic depolyment with ansible allows for a large number of machines to be distributed over a network.  

The playbook implements the following tasks:
- Download image
- Install Docker
- Configuration

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

https://github.com/Dru-Ha/ELK-Stack_Project/pull/1

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- 10.0.0.5
- 10.0.0.6

We have installed the following Beats on these machines:
- Filebeat

These Beats allow us to collect the following information from each machine:
-Filebeat records changes to files and logs.  It should show information on the installation or updating of software.
-Metricbeat records the system metrics.  It should show increases in the use of resources, such as memory/CPU used and amount of time operated by the user.  


### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the playbook file to the /files directory.
- Update the playbook file to include necessary authorized connections.
- Run the playbook, and navigate to 13.66.36.60:5601/app/kibana to check that the installation worked as expected.

- filebeat-config.yml must be moved to the /files
- You must update the playbook to make Ansible run the playbook on a specific machine. 
- Specify which machine to install the ELK server on versus which to install Filebeat on by specifying the address of the machine
- Navigate to 13.66.36.60:5601/app/kibana in order to check that the ELK server is running.

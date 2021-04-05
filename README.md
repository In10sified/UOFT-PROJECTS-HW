# UOFT-PROJECTS/HW
 HOMEWORKS & PROJECTS
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

!https://github.com/In10sified/UOFT-PROJECTS-HW/tree/main/Diagrams

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  https://github.com/In10sified/UOFT-PROJECTS-HW/blob/main/Ansible/filebeat-playbook-yml.txt

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting inbound access to the network.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the Health of the VMS and system
- Filebeat looks for modifications thats been made to the file system.
- Metricbeat looks for the chages in the system metrics.

The configuration details of each machine may be found below.

| NAME    | FUNCTION | IP ADDRESS    | OPERATING SYSTEM |
|---------|----------|---------------|------------------|
| JUMPBOX | GATEWAY  | 20.51.200.113 | LINUX            |
| WEB-1   | SERVER   | 10.0.0.5      | LINUX            |
| WEB-2   | SERVER   | 10.0.0.6      | LINUX            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the JUMPBOX machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:

Machines within the network can only be accessed by SSH
A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 10.0.0.1:254         |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...

The playbook implements the following tasks:

- Install docker on all network machines so they will be able to recieve and install containers
Ansible is installed on the Jump Box VM to distribute containers to other VMs on the network
Ansible playbooks are used to install the ELK stack container on the ELK server and a 'Beats' containers on the Web servers


The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

https://github.com/In10sified/UOFT-PROJECTS-HW/blob/main/Diagrams/docker_Output.png

### Target Machines & Beats
This ELK server is configured to monitor the following machines:

Web-1: 10.0.0.5
Web-2: 10.0.0.6

We have installed the following Beats on these machines:
- Filebeat was successfully installed on both of the VMS

These Beats allow us to collect the following information from each machine:
- Filebeat allows us to collect raw log data from the machines and displays it with a nice UI in the Kibana Logstash. 

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the YML files to Ansible Directory.
- Update the Hosts file to include...
- Run the playbook, and navigate to kibana to check that the installation worked as expected.

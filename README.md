# azure-cloud-security-architecture
this is a full description on building your own cloud virtual machine and security
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

https://github.com/babtunee/azure-cloud-security-architecture/blob/master/Diagram/cloud-network-architect.png
These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the repository file may be used to install only certain pieces of it, such as Filebeat.

 https://github.com/babtunee/azure-cloud-security-architecture/tree/master/Ansible
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
- Load balancer protect the application layer of the OSI model. one advantage of Jumpbox is that it forces all traffic through a single node.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the configuration and system application
- _TODO: What does Filebeat watch for? log monitoring
- _TODO: What does Metricbeat record? operating system such as CPU, Memory

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.1   | Linux            |
| Web-1    | container| 10.0.0.8   | Linux            |
| Web-2    | container| 10.0.0.9   | Linux            |
| Web-3    | container| 10.0.0.10  | Linux            |
| ELKserver| Monitor  | 10.0.0.4   | linux

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses: 74.101.199.201


Machines within the network can only be accessed by jumpbox via ssh.
- _TODO: Which machine did you allow to access your ELK VM?
jumpbox is allows to access ELK VM with IP 10.1.0.7

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box |       Yes           | 74.101.199.201       |
|          |       No            | 10.1.0.7             |
|          |       No            | 10.1.0.7             |
|web-3     |       No            | 10.1.0.7
|ELKserver |       yes           | 74.101.199.201 via 5601 

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because it eliminates the chance of human error and can simplifies the process of configuring potentially thousands of machines identically all at once.

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

https://github.com/babtunee/azure-cloud-security-architecture/blob/master/Diagram/elk-container.png

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
web-1, web-2, and web-3 with ip address 10.1.0.8, 10.1.0.9, 10.1.0.10 respectively.

We have installed the following Beats on these machines:
Filebeat and Metricbeat

These Beats allow us to collect the following information from each machine:

Filebeat monitors the log files or locations that you specify, collects log events, and forwards them either to Elasticdearch or Logstash for indexing. E.g syslog

Metricbeat periodically collects metrics from the operating system and from service running on other server. It takes the metrics and statistics that it collects and ships them to the output that you specify, such as Elasticsearch or Logstash. E.g memory usage

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the file to ansible-config.yml.
- Update the ansible-config.yml file to include username of your VMs  
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._

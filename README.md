## Automated ELK Stack Deployment

**The files in this repository were used to configure the network depicted below.

![Diagram Image](https://github.com/AngelaReidMcIntosh1234/ELK-Stack-Project/blob/main/ELK%20Stack%20Project.drawio.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the ansible file may be used to install only certain pieces of it, such as Filebeat.

 Enter the playbook file: **/etc/ansible/install-elk-playbook.yml

**This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
- Beats in Use
- Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

**The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly efficient, in addition to restricting traffic to the network.
- What aspect of security do load balancers protect? What is the advantage of a jump box?_

**Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the log traffic and system traffic.

 **What does Filebeat watch for?
 
 -Filebeat watches for any information in the file systemwhich has been changed and when it has.
 -Filebeats watches for log files/location and collects log events
 
**What does Metricbeat record?

- -Metric beat takes the metrics and statics that collects and ships them to hte outpus you specify
- Metricbeats records metric and statistical data from the operating system and from services running on the server

**The configuration details of each machine may be found below.

| Name     | Function | IP Address | Operating System  |
|----------|----------|------------|------------------ |
| Jump Box | Gateway  | 10.0.0.1   | Linux Ubuntu 18.04|
| Web-1    | Server   | 10.0.0.4   | Linux Ubuntu 18.04|
| Web-2    | Server   | 10.3.0.5   | Linux Ubuntu 18.04|
| Web-3    | Server   | 10.2.0.4   | Linux Ubuntu 18.04|
|ELK_VM1   |ELK Server| 10.3.0.4   | Linux Ubuntu 18.04| 
 

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the JumpBox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
      Add whitelisted IP addresses
      Public IP: 40.87.68.147

**Machines within the network can only be accessed by SSH.

Which machine did you allow to access your ELK VM? What was its IP address?
-1. The JumpBox
-2. Vnet IP 10.0.0.1

**A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | 10.0.0.1 10.0.0.2    |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

**Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...

-What is the main advantage of automating configuration with Ansible?
    This allows you to deploy to multiple servers using a single playbook

**The playbook implements the following tasks:
 -In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
 -Install docker.io
 -install docker container
 -Launch docker container: ELK 1VM
 

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

 Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)
 ****Unable to upload screenshoot to Github****

### Target Machines & Beats
This ELK server is configured to monitor the following machines:

**List the IP addresses of the machines you are monitoring
Web-1, IP Address: 10.0.0.4
Web-2, IP Address: 10.3.0.5
Web-3, IP Address: 10.2.0.4

We have installed the following Beats on these machines:
 Specify which Beats you successfully installed
 -Filebeat
 -Metricbeat

**These Beats allow us to collect the following information from each machine:
 In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc.
 
 -Filebeats monitors log files or locations you specify, collect log events, and forward them either to elastic
 -Metric collects metrics from the operating system and from services running on the server
 

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

**SSH into the control node and follow the steps below:

- Copy the Playbook file to /etc/ansible.
- Update the configuration file to include the webservers and ELK VM (Private IP Address)
- Run the playbook, and navigate to ELK VM to check that the installation worked as expected.

 **Answer the following questions to fill in the blanks:
 
- _Which file is the playbook? Where do you copy it?_
**/etc/ansible/ansibleplaybook.yml | filebeat_configuration.yml

**Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?
   **/etc/ansible/hosts ansibleplaybook.yml
- 
**Which URL do you navigate to in order to check that the ELK server is running?
http://[ELK1-VM.External.IP]:5601/app/kibana

**As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc.
/etc/ansible/roles/directory

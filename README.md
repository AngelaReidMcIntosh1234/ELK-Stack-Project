Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted above.

They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the ansible file may be used to install only certain pieces of it, such as Filebeat.

/etc/ansible/install-elk-playbook.yml

This document contains the following details:

Description of the Topologu
Access Policies
ELK ConfigurationThese files have been tested and used to generate a live ELK deployment on Az
Beats in Use
Machines Being Monitored
How to Use the Ansible Build
Description of the topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.
Load balancing ensures the application will be highly efficient in addition to restricting traffic to the network.

What aspect of security do load balancers protect? What is the advantage of a jump box?_-

Load balancer protects the system from DDos attacks by shifting attack traffic.
Load balancing contributes to the availability aspect of security in regards to the CIA triad.
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the log and system traffic.

What does Filebeat watch for?_
-Filebeat watches for any information in the file system which has been changed and when it has.
-Filebeat watches for log files/locations and collects log events.

What does Metricbeat record?

Metricbeats takes the metrics and statics that collect and ships them to the output that you specify.
Metricbeat records metric and statistical data from the operating system and from services running on the server.
The configuration details of each machine may be found below:

| Name | Function | IP Address | Operating System
|__________ ||_ |_____________________
JumpBox | Gateway |10.2.0.3 |Linux Ubuntu
| Web-1 | Server |10.0.0.4 |Linux Ubuntu
| Web-2 | Server |10.3.0.5 |Linux Ubuntu
| Web-3 | Server | 10.2.0.4 |Linux Ubuntu
| ELK-VM1| Server |10.3.0.4 |Linux Ubuntu

Access Policies
The machines on the internal network are not exposed to the public Internet.

Only the JumpBox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
Add whitelisted IP address ---Public IP address which changes every time when VM is on/off: 40.87.68.147

Machines within the network can only be accessed by SSH.
Which machine did you allow to access your ELK VM? What was its IP address?

JumpBox VM - 10.2.0.3
A summary of the access policies in place can be found in the table below.

Name	Publicly Accessible	Allowed IP Addresses
Jump Box	Yes/No	10.2.0.3 10.2.0.3
ELK Configuration
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
What is the main advantage of automating configuration with Ansible?_
This allows you to deploy to multiple servers using a single playbook

The playbook implements the following tasks:
In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
-sudo docker ps

/etc/ansible/install_elk.yml
navigate to http:// [ELK1.ELK_VM.External.IP]:5601/app/Kibana
We have installed the following Beats on these machines:
Specify which Beats you successfully installed_

These Beats allow us to collect the following information from each machine:
-: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., Winlogbeat collects Windows logs, which we use to track user logon events, etc._

Elastic____________________________________________________________________________________________________________________________________________________________
|Enterprise Search| | Observability |Security |Analytics
|________________________________________ ||_________ |__________________________________________
|Create search experience |Consolidate your metrics, |Prevent, collect, detect and respond |Explore, visualize, and analyze
|with a refined set of API and tools |application traces, and system|and respond to threats for unified |your data using a powerful
| |availability with purpose |protection across infrastructure |suite of analytical tools and
| |built UIs | |applications
| | | |

Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:
/etc/ansible/file/filebeat-configuration.yml

SSH into the control node and follow the steps below:

Copy the filebeat.yml file to /etc/ansible/ELK1

Update the configuration file to include ELK 1 private IP: 10.3.0.4

Run the playbook, and navigate to ____ to check that the installation worked as expected.

Answer the following questions to fill in the blanks:_

Which file is the playbook? Where do you copy it?_
cp filebeat.yml | /etc/ansible /elk1plabo.txt

_Which URL do you navigate to in order to check that the ELK server is running?

http:// [ELK 1-VM.External.IP]: 5601/app/Kibana

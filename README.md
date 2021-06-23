# ELK-Project1-
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

https://drive.google.com/file/d/1aUNGKZChFn7y3sRkEWXIMjtX6wG2Phr1/view?usp=sharing

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _YAML____ file may be used to install only certain pieces of it, such as Filebeat.

elk-playbook.yml
https://drive.google.com/file/d/1sK9uKU83MXLaNI5KuaqgoR_ftZ29wPDV/view?usp=sharing 

This Document contains the following details:
-Description of the Topology
-Access Policies 
-ELK Configuration
 - Beats in Use
 - Machines Being Monitored 
-How to use the Ansible Build 

### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly _protected____, in addition to restricting _access____ to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_

Load balancers protects the system from DDoS attacks by shifting attack traffic. The advantage of a jump box is to give access to the user from a single node that can be secured and monitored.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _jumpbox____ and system _network____.
- _TODO: What does Filebeat watch for?_
Filebeat watches for file changes on the machine.

- _TODO: What does Metricbeat record?_
Metricbeat collects metrics from the operating system and from the services running on the server.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function  | IP Address | Operating System |
|----------|---------- |------------|------------------|
| Jump Box | Gateway   | 10.0.0.0   | Linux            |
| Web-1    | Webserver | 10.0.0.5   | Linux            |                  
| Web-2    | Webserver | 10.0.0.6   | Linux            |                  
| ELK-VM   | Webserver | 10.1.0.4   | Linux            |                  

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the _jump box provisioner____ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_

5601 Kibana Port 

Machines within the network can only be accessed by _jump box provisioner____.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?

My PC – 47.132.64.66

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 |   47.132.64.66       |
| Web-1    | NO                  |   10.1.0.4           |
| Web-2    | NO                  |   10.1.0.4           |
| ELK-VM   | NO                  |   10.1.0.4           |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_


The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._

-	Install docker.io
-	Install pip3
-	Install docker python module
-	Increase virtual memory
-	Download and launch a docker

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_

Web-1  10.0.0.5
Web-2  10.0.0.6

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

Microbeats

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _playbook____ file to _Ansible Control Node____.
- Update the _hosts____ file to include...
- Run the playbook, and navigate to _Kibana___ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._

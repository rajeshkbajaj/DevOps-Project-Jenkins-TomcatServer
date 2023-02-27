## DevOps Project 

The Project is about deploying a Java based Web Application on Tomcat Server.
Created 2 EC2 instance on AWS:
1. Created Jenkins Master EC2 on public subnet: Installed Java, Jenkins and accessed the jenkins from webui. Installed necessary plugins ( git,maven,deploy to container e.t.c..).
Manage jenkins - Global Tool Configuration - Added Maven,jdk homepath.
Manage credentilas - Added Tomcat user name and password
Installed Ansible, Created a inventory and playbook file for installing Java and Tomcat on Appserver
Created a maven project, cloned the repository from git, applied clean install and deployed web artifacts webapp.war on tomcat server

2. Created App server (Tomcat) EC2 on Private subnet. From Jenkins EC2, SSH into App server through Bastion jump file.
created a AppLoadBalancer and added App server as Target group
verified tomcat server status through "sudo systemctl status tomcat" and it was runing successfully
started the tomcat server from /opt/tomcat/bin/startup.sh and accessed the webui from Appl Load Balancer DNS:8080.
modefied the conf files to create user accounts


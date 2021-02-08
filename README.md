This playbook will install r1soft server on Centos 7 and r1soft agent on Centos 6

R1soft is the fast, reliable and affordable server backup management.

First we are installing a r1soft server, and these are steps which we will follow:

1.Step:

# cd /etc/yum.repos.d
# vi r1soft.repo 

 Insert the following text into the file and save the file:
 
[r1soft]
name=R1Soft Repository Server
baseurl=http://repo.r1soft.com/yum/stable/$basearch/
enabled=1
gpgcheck=0 

 To verify what is written to the file, use the following command:
 # cat /etc/yum.repos.d/r1soft.repo  
 
 With the installed YUM repository, you can use the following command to install the CDP Enterprise Server:
  # sudo yum install r1soft-cdp-enterprise-server -y
  
  2.Step:
  Copy ssh keys from r1soft server  to remote hosts
  
  3.Step:
  Add hosts to the inventory file 
  vi /etc/ansible/hosts
  [r1soft]
  Ip address of server
  
  4.Step
  Git clone and Run the r1soft-server.yml playbook
  
  Now our r1soft server is ready and it is time to install r1soft agent
  
   cd /etc/yum.repos.d
vi r1soft.repo 
Insert the following text into the file and save the file:


 [r1soft]
name=R1Soft Repository Server
baseurl=http://repo.r1soft.com/yum/stable/$basearch/
enabled=1
gpgcheck=0 

Once you have configured the YUM repository, you can use the following command to install the Backup Agent:
sudo yum install serverbackup-enterprise-agent 


  
  r1soft-agent.yml playbook is ready for use, clone it, change servers ip and run the playbook

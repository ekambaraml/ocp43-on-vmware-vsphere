# ocp43-on-vmware-vsphere
Deploying OpenShift 4.3 on Vsphere UPI Infrastructure



## Setup Install server

1. Create a RHEL machine with network access openshift nodes vms.
2. Disable firewall and selinux

  #### Stop the firewall and set selinux to passive
  
  ```
  systemctl stop firewalld
  systemctl disable firewalld
  
  setenforce 0
  sed -i 's/SELINUX=enforcing/SELINUX=disabled/' /etc/selinux/config
  ```
3. Install httpd webeserver
  ```
  yum install -y httpd
  mkdir /opt/ocp
  ln -s /opt/ocp /var/www/html/ocp
  ```
4. Download the openshift client and installers from redhat site and expand into /opt/ocp directory
   make sure you download from the latest 4.5x installers. https://mirror.openshift.com/pub/openshift-v4/clients/ocp/4.5.19/
   
   cp /opt/ocp
   wget https://mirror.openshift.com/pub/openshift-v4/clients/ocp/4.5.19/openshift-install-linux.tar.gz
   wget https://mirror.openshift.com/pub/openshift-v4/clients/ocp/4.5.19/openshift-client-linux.tar.gz
   


#Setup Instructions

##Virtualization Setup
*install virtualization software*
`sudo yum groupinstall "Virtualization Host"`
`sudo yum install libvirt virt-manager virt-viewer`
`systemctl enable libvirtd.service`
`systemctl start libvirtd.service`

##Vagrant Setup
*install vagrant*
`mkdir ~/Downloads`
`cd ~/Downloads`
`wget https://releases.hashicorp.com/vagrant/1.9.1/vagrant_1.9.1_x86_64.rpm`
`rpm -ivh vagrant_1.9.1_x86_64.rpm`

##Vagrant Box Configuration
*initialize vagrant*
`mkdir ~/boxes`
`cd ~/boxes`
`git clone https://github.com/bdurepo1/redhat_libvirt_cdk.git`
`wget https://developers.redhat.com/download-manager/file/rhel-cdk-kubernetes-7-33.x86_64.vagrant-libvirt.box`
`vagrant box add rhel-cdk-kubernetes-7-33.x86_64.vagrant-libvirt.box rhel`
`vagrant plugin install vagrant-libvirt --plugin-version 0.037`
`vagrant plugin install vagrant-service-manager --plugin-version 1.4.0`
`vagrant up`

##Openshift Service Initialization
*within vagrant box*
`vagrant ssh`
`sudo su -c systemctl enable openshift.service`
`sudo su -c systemctl start openshift.service`
`exit`

##Openshift Shell Environment Configuration
*on the virtualization host*
`eval "$(vagrant service-manager env openshift)"`

##Openshift Access and Documentation
*openshift web console username admin password admin*
[Openshift Developers](https://developers.openshift.com/)
[Red Hat Container Registry](https://access.redhat.com/containers)

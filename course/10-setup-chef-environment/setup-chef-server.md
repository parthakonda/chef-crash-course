# Setup chef server

# Installing chef-server in AWS EC2 ubuntu 18.x

## Configure `hosts` & `hostname`

    By default these will take the internal ip of the ec2. This is one of the stopping point or hard thing to go through.

`sudo vi /etc/hosts`

    127.0.0.1 <public_ip_or_domain>

    # The following lines are desirable for IPv6 capable hosts
    ::1 ip6-localhost ip6-loopback
    fe00::0 ip6-localnet
    ff00::0 ip6-mcastprefix
    ff02::1 ip6-allnodes
    ff02::2 ip6-allrouters
    ff02::3 ip6-allhosts

`sudo vi /etc/hostname`

    <public_ip_or_domain>

## Reboot the instance

    sudo reboot

## Install required packages
```
    sudo apt-get update -y
    sudo apt-get upgrade -y
    wget https://packages.chef.io/files/stable/chef-server/12.18.14/ubuntu/18.04/chef-server-core_12.18.14-1_amd64.deb
    sudo dpkg -i chef-server-core_12.18.14-1_amd64.deb
    rm chef-server-core_12.18.14-1_amd64.deb
    sudo chef-server-ctl reconfigure
    mkdir .chef
    sudo chef-server-ctl user-create <user> <first_name> <last_name> <email@company.com> '<password>' --filename ~/.chef/<user>.pem

    sudo chef-server-ctl user-create partha partha saradhi parthasaradhi.konda@gmail.com 'Random@123' --filename ~/.chef/partha.pem
    
    sudo chef-server-ctl org-create <org_name> "<org_name_detailed>" --association_user <user> --filename ~/.chef/<org_name>.pem

    sudo chef-server-ctl org-create kodekart "kodekart" --association_user partha --filename ~/.chef/kodekart.pem
```
## Installing chef-manage
   This is to provide UI for chef-server where you can manage things easily.
```
    sudo chef-server-ctl install chef-manage
    sudo chef-server-ctl reconfigure
    sudo chef-manage-ctl reconfigure
```


There you go, you're all set. Hit your public ip

http://<your_public_ip>

Ref:
https://www.linode.com/docs/applications/configuration-management/install-a-chef-server-workstation-on-ubuntu-18-04/

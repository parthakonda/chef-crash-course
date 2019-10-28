# Chef crash course
This course is designed for beginners with no prior knowledge on ruby or sysops. One can complete this course in 4 to 5hrs. By end of this course you'll be able to setup whole chef environment and able to write your cookbooks.

# Target Audience
Anyone who is having software engineering background. No prior knowledge on ruby is required.

# Course duration
4 to 5hrs

# Artifacts
- Diagrams
- Theory wiki
- Example cookbooks

# Course Contents

# Traditional
## Create Play area
- Provision or create some linux box in Local/vagrant/VM/AWS

## Connecting
- Understanding SSH
- SSH from one box to another box
- Understanding SCP

## Installing nginx
- Installing Nginx in the remote server

## Networks
- Understanding networking at highlevel
    - Public network
    - Private network

## Shell Vs tools
- Pros & cons with shell
- Pros & cons with tools (chef, ansible, puppet, fabric, etc..)

## The Landscape
- Understanding the landscape of the tools

## Chef & Terminology
- What is chef?
- Chef Server
- Chef Workstation
- Chef Node
- Chef server-ctl
- Chef manage
- Chef dk
- knife
- berkshelf
- supermarket

## Chef Architecture
- Understanding how chef works

## Chef tech stack
- Understanding different tech stack items of chef

## Setup chef environment
- Setup server
- Setup workstation

## Process of getting started (handshake workstation & Server)
- Configuring chef server
    - Creating Org
    - Creating User
    - Associating User to org
- Configuring chef workstation
    - Setup knife

# Ruby essentials
- Setup Ruby
- Skeleton
- Variables
- String formatting
- methods
- blocks

## Understanding chef-repo and basic building blocks
- Understanding folder structure
- Understanding chef-repo
- Understanding cookbooks
- Understanding recipes
- Understanding resources
- Understanding databags
- Understanding environments
- Understanding roles

## Writing your first cookbook
- Resource identification
- Syntax
- Installing nginx on node

## Bootstrapping a new node/target machine
- Understanding kitchen.yml
- Bootstraping a new node/target machine
- Understanding run_list

## Using public cookbooks
- Understanding supermarket

## Publishing your cookbook
- Understanding uploading your cookbook

## Misc
- Using data_bags
- Using templates
- knife upload Vs berks upload (dependacy management)

# Author
ParthaSaradhiKonda<<parthasaradhi.konda@gmail.com>>
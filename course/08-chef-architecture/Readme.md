# Understanding Chef Architecture

## Chef Server
   This is where all the resources will get stored and pulled. Both client and Node will pull the required resource from here. In other words, configuration will be maintained at here.

   The responsibities are

   - Manage Configuration
   - Manage Organisations
   - Manage users
   - Manage data

## Chef Workstation
   This is from where you're going to writing and executing your cookbooks. This is a client where all the development is done and pushed to server.

   - Cookbooks get created
   - Cookbooks get uploaded

## Chef Node/Target
   This is the target machine which gonna bootstraped and orchestrated.

## Chef Server-ctl
   This is used to control the chef-server

## Chef manage
    This is used to manage different chef server resource i.e., organizations, users.

## Chef DK (Development Kit)
    This will install chef-client in the workstation and also provide ruby gems, libraries, commandline utilities.

## Chef Repo
    This is a place where all of the configuration and cookbooks will get stored. And using knife will sync everything with Chef Server.

    - Cookbooks
    - Roles
    - DataBags
    - Environments
    - Configuration Files

## Chef cookbook
    A cookbook is a collection of your recipes - Collection of shell script

## Chef recipe
    A recipe is a collection of resources - Shell script

## Chef resource
    A recipe is a basic building block which instructs the server to do specific action - Its like a shell command
    
    A resource can be (default)
    
    - package − Manages the packages on a node
    - service − Manages the services on a node
    - user − Manages the users on the node
    - group − Manages groups
    - template − Manages the files with embedded Ruby template
    - cookbook_file − Transfers the files from the files subdirectory in the cookbook to a location on the node
    - file − Manages the contents of a file on the node
    - directory − Manages the directories on the node
    - execute − Executes a command on the node
    - cron − Edits an existing cron file on the node

## Knife
    cli tool that act as an interface between your workstation chefrepo and chef server.

    Sync the code/data/configuration(i.e., chef-repo) between your workstation and server

    And it is used to manage the following

    - Node
    - Cookbooks and recipes
    - Roles, Environment and DataBags
    - Installing chef infra client in nodes (which installs chef agent in the node)
    - Searching indexed data in server

## Berkshelf
    Its a dependancy manager. Will sync the public repos from chef server to workstation. And its like pip for python, apt for ubuntu, yum for linux, etc.,

## Supermarket
    It's an open source community where you can get publicly available cookbooks. And you can push your too.

## Bootstrapping a Node
    The process of installing chef-agent in the target machine, pulling configuration from chef-server and install the required things (runlist) in the target machine from workstation is called bootstrapping.


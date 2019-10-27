# Installing & Configuring chef workstation

chef-workstation: A client having knife installed can be called as workstation.
# Make sure that you've ruby got installed
```
    sudo apt-get update
    sudo apt-get install ruby-full
```

## Installing knife & chefdk

    sudo gem install knife
    sudo gem install chef-dk

or

    wget https://packages.chef.io/files/stable/chefdk/3.1.0/ubuntu/18.04/chefdk_3.1.0-1_amd64.deb
    sudo dpkg -i chefdk_*.deb
    rm chefdk_*.deb

## Create a chef app repo

    chef generate app chef-repo
    cd chef-repo

Make sure that .chef exists to store the `knife.rb`

    mkdir .chef

## Add the RSA Private KeysPermalink

The RSA private keys generated when setting up the Chef server now need to be placed on the workstation. The process behind this will vary depending on whether or not you are using SSH key pair authentication to log into your Linodes.

If you are not using key pair authentication, copy the file directly from the Chef Server. Replace user with your username on the server, and 192.0.2.0 with the URL or IP of your Chef Server:

    scp user@192.0.2.0:~/.chef/*.pem ~/chef-repo/.chef/

If you are using key pair authentication, then from your local terminal copy the .pem files from your server to your workstation using the scp command. Replace user with the appropriate username, and 192.0.2.0 with the URL or IP for your Chef Server and 203.0.113.0 with the URL or IP for your workstation:

    scp -3 user@192.0.2.0:~/.chef/*.pem user@203.0.113.0:~/chef-repo/.chef/

Confirm that the files have been copied successfully by listing the contents of the .chef directory:

    ls ~/chef-repo/.chef

Add the RSA Private KeysPermalink
The RSA private keys generated when setting up the Chef server now need to be placed on the workstation. The process behind this will vary depending on whether or not you are using SSH key pair authentication to log into your Linodes.

If you are not using key pair authentication, copy the file directly from the Chef Server. Replace user with your username on the server, and 192.0.2.0 with the URL or IP of your Chef Server:

    scp user@192.0.2.0:~/.chef/*.pem ~/chef-repo/.chef/

If you are using key pair authentication, then from your local terminal copy the .pem files from your server to your workstation using the scp command. Replace user with the appropriate username, and 192.0.2.0 with the URL or IP for your Chef Server and 203.0.113.0 with the URL or IP for your workstation:

    scp -3 user@192.0.2.0:~/.chef/*.pem user@203.0.113.0:~/chef-repo/.chef/
Confirm that the files have been copied successfully by listing the contents of the .chef directory:

    ls ~/chef-repo/.chef

Your .pem files should be listed.Your .pem files should be listed.


# Generate knife.rb

- Create a knife configuration file by navigating to your ~/chef-repo/.chef folder and creating a file named knife.rb in your chosen text editor.

- Copy the following configuration into the knife.rb file:
`~/chef-repo/.chef/knife.rb`

        current_dir = File.dirname(__FILE__)
        log_level                :info
        log_location             STDOUT
        node_name                'node_name'
        client_key               "USER.pem"
        validation_client_name   'ORG_NAME-validator'
        validation_key           "ORGANIZATION-validator.pem"
        chef_server_url          'https://example.com/organizations/ORG_NAME'
        cache_type               'BasicFile'
        cache_options( :path => "#{ENV['HOME']}/.chef/checksums" )
        cookbook_path            ["#{current_dir}/../cookbooks"]

- Change the following:

The value for node_name should be the username that was created on the chef server.
Change USER.pem under client_key to reflect your .pem file for your user.
The validation_client_name should be your organization’s ORG_NAME followed by -validator.
ORGANIZATION-validator.pem in the validation_key path should be set to the ORG_NAME followed by -validator.pem.
Finally the chef_server_url needs to contain the IP address or FQDN of your Chef server, with your ORG_NAME.

- Move to the chef-repo directory and copy the needed SSL certificates from the server:

    cd ..
    knife ssl fetch

- Confirm that `knife.rb` is set up correctly by running the client list:

    knife client list

This command should output the validator name.

With both the server and a workstation configured, it is possible to bootstrap your first node
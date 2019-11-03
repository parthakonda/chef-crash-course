# Understanding roles in chef

Assume that you're a frontend engineer and your responsibilites are writing some UI related code and it is by your role.

As a backend engineer, my responsibilities are developing some API end-points and doing server side scripting for achieving different business functionalities and it is by your role.

So, if somebody is assigned with a role means they are having a set of responsibilities.

A role in chef is nothing but grouping set of cookbooks/recipes/attributes/environments together.

Assume that there 5 recipes in a cookbook.

Recipe - 1: Update the apt

Recipe - 2: Install nginx

Recipe - 3: Create some file

Recipe - 4: Get status of the server

Recipe - 5: Shutdown the server


And there are 3 persons who can do the following

Person - 1: Who will just take care of installation
    Only Recipe - 1

Person - 2: Who will just check the status
    Recipe - 4

Person - 3: Who will Create some file and get some status.
    Recipe - 3, Recipe - 4

Person - 4: Who will just shutdowns the server
    Recipe - 5


## How to create a role
```
knife role create <role_name>
```

Note: The above will asks you for EDITOR env variable setting. Set it to some of your faviorate editor. I use nano so I set `export EDITOR=nano`

This will open a json file in selected editor. Specify a run_list for your role.

```
{
    "name": "target",
    "description": "",
    "json_class": "Chef::Role",
    "default_attributes": {

    },
    "override_attributes": {

    },
    "chef_type": "role",
    "run_list": [
        # List of things needs to be executed
    ],
    "env_run_lists": {

    }
}
```


## Bootstrap with role
```
knife bootstrap <ip> --ssh-user <user> --sudo --ssh-identity-file <pem_file> --node-name <node_name> --run-list 'role[<role_name>]' -y
```
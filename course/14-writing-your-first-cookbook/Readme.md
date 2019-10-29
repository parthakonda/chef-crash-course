# Writing your first cookbook

Goal:
Let's take the same use case that we've manually achieved in previous section.

### Use case/Problem statement
Alice - An employee at google, asked to get a new webserver. And the technical breakdown for this as below

- First spin up a new instance
- Install a nginx webserver
- Start the webserver
- Test whether the webserver is accepting the requests are not.
- If webserver is working fine then customize the home page and make sure it displays the following information
<br>
`Welcome to WebServer`

### Thought process
- Need to have an instance/Play area where the nginx needs to be installed.
- Create a chef repo
- We need to create our chef repo where our cookbooks located.
- Identify the recipe/recipes to perform the required task
- Push the cookbooks to server
- Bootstrap the target node.

Assuming that we already have a target node up and running.

## Creating chef repo
```
chef generate app nginx-sample
```

### Create cookbook/use default cookbook
```
chef generate cookbook nginx
```

### Identify the resources/commands needs to be executed.

- What is resource?
A resource is a statement of configuration policy that:

    - Describes the desired state for a configuration item
    - Declares the steps needed to bring that item to the desired state
    - Specifies a resource type—such as package, template, or service
    - Lists additional details (also known as resource properties), as necessary
    - Are grouped into recipes, which describe working configurations

- Resource syntax
```
type 'name' do
   attribute 'value'
   action :type_of_action
end
```
Example:
```
package 'tar' do
  version '1.16.1'
  action :install
end
```

- Resource types
Following are some of the resources comes by defaut

    - service
    - package
    - file
    - template
    - execute
    - bash
    - cron
    - git
    - apt_package

Let's recap the steps

1. Update the apt
2. Install nginx package
3. Restart the nginx service

Create the recipe using `execute` resource

`nginx.rb`
```
# update apt
execute 'update_apt' do
  command 'sudo apt-get update'
end

# install nginx
execute 'install_nginx' do
  command 'sudo apt-get install nginx'
end

# restart the service
execute 'restart_service' do
  command 'sudo service nginx restart'
end
```





OR




- Using available resources
  - resource for update apt
    ```
    apt_update 'name' do
        frequency      Integer # default value: 86400
        action         Symbol # defaults to :periodic if not specified
    end
    ```
  - resource for package nginx
    ```
    apt_package 'name' do
        default_release              String
        options                      String, Array
        overwrite_config_files       true, false # default value: false
        package_name                 String, Array
        response_file                String
        response_file_variables      Hash
        timeout                      String, Integer
        version                      String, Array
        action                       Symbol # defaults to :install if not specified
    end
    ```
  - resource for service start/restart
    ```
    service 'name' do
        init_command         String
        options              Array, String
        parameters           Hash
        pattern              String
        priority             Integer, String, Hash
        reload_command       String, false
        restart_command      String, false
        run_levels           Array
        service_name         String # default value: 'name' unless specified
        start_command        String, false
        status_command       String, false
        stop_command         String, false
        supports             Hash # default value: {"restart"=>nil, "reload"=>nil, "status"=>nil}
        timeout              Integer
        user                 String
        action               Symbol # defaults to :nothing if not specified
    end
    ```

- Bringing all together
`nginx.rb`
```
# Update apt
apt_update 'update_apt'

# Install nginx package
apt_package 'nginx'

# Start/Restart the service
service "nginx" do
  action :restart
end
```


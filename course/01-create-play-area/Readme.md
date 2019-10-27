# Creating play area

All we're trying to understand is why & what chef is actually doing. Let's take some real-time use case. 

Chef is all about automating the process. So before learning automation let's see the manual steps first.

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
There are 3 parts in the above requirement. First one is to spin up the new hardware, Second one is to install the nginx and start the server and the third is to test whether the server is accepting requests or not.

Creating play area or spin up the hardware where you want to install the required things.

# For example, create an ec2 in AWS
- Go to aws management console
- Select EC2
- Click on Launch Instance
- Give appropriate configuration such as instance type, disk, security groups, network(vpc) and tags.
- Review & launch the instance


The process of spinning up the hardware is called `provisioning infrastructure`. And in the above we've provisioned the ec2 in aws successfully.
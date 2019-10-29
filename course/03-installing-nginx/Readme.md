# Installing Nginx on remote machine

## Recap the use-case that we're solving
### Use case/Problem statement
Alice - An employee at google, asked to get a new webserver. And the technical breakdown for this as below

- First spin up a new instance - Done
- Install a nginx webserver
- Start the webserver
- Test whether the webserver is accepting the requests are not.
- If webserver is working fine then customize the home page and make sure it displays the following information
<br>
`Welcome to WebServer`

In the previous section, we've successfully provioned our required hardware. Now we want to do the next step in the solution i.e., `install webserver` and understood the required protocol (and how it works) to connect to the target system. 

Now let's connect to the target system and install the required package.

## Brief about nginx
Nginx is a webserver and can also act as load balancer. And can serve static content. As a devops guy the above information is good enough. Now let's install the nginx.

## Steps to install the nginx

```
# Update the system
sudo apt-get update

# Install nginx
sudo apt-get install nginx -y

# Start nginx server
sudo services nginx start
```

[TODO]: Add windows installation too.

## Verifying that nginx got installed or not
Let's visit the public ip of the server with port 80

http://<public_ip>:80 or http://<public_ip>

[TODO]: Add ip if local setup

## Customising the home page
So far, we've successfully installed the nginx. Now let's customize the home page.

By default, nginx will serve the html from `/var/www/html`. We just need to create a file called `index.html` in that folder. So that, it will serve this file.

`index.html`
```
<html>
    <head>
    </head>
    
    <body>
        <h1>Welcome to WebServer</h1>
    </body>
</html>
```

## Restart the webserver
```
sudo service nginx restart
```

## Verifying that nginx got updated html or not
Let's visit the public ip of the server with port 80

http://<public_ip>:80 or http://<public_ip>

You should be able to see the content `Welcome to WebServer`

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
Need to have an instance/Play area where the nginx needs to be installed.
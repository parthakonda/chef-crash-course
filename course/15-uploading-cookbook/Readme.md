# Uploading a cookbook to the chef-server

What we've done so far is `created our code`. Now by using it we need to achieve (installing nginx) our requirement.

Before we bootstraping any target node first our cookbooks needs to be uploaded into server. And then target node can pull that information to configure itself.

# Command to upload
Syntax:
```
knife cookbook upload <cookbook>
```

# Verify at server


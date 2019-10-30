# Using public repos

So far we've achived the following

- Manually setup the nginx
- Automated through our own cookbook using `execute` resource
- Automated through available resources


Now,

For example, if someone already solve this problem and contributed to open-source (either supermarket or some other registry) then we can use those recipes/resources and get our work done.

# Finiding & Installing required cookbooks

Chef supermarket will maintain all the publicly available cookbook. And using knife you can interact with supermarket to see, search, download and install the required cookbook.

`knife supermarket <command>`

- List all the available cookbooks

    `knife supermarket list`

- Search the cookbook

    `knife supermarket search <pattern>`

- Download the cookbook

    `knife supermarket download <cookbookname> [<version>]`

- Install the cookbook

    `knife supermarket install <cookbookname> [version]`

# Using the installed cookbooks in anoter cookbook

Like any other programming language we need to mention the depedency in the metadata.rb of cookbook where we want to use. Then we can use the resources available in it.

`metadata.rb`
```
...
# Add at the bottom
# Example:
# depends '<cookbook', '~> <version>'
depends 'nginx', '~> 10.0.2'
```

# Upload the cookbook to chef-server to get the latest chages

```
knife cookbook upload <installed_cookbook>
knife cookbook upload <desired_cookbook>
```

# Understand the problem of internal dependancy
If we install any dependancy then the depedencies of it also needs to be present in the server. So download all the dependencies and push to the server.


# Using the available resource
Once you specified your dependency in `metadata.rb` then you can use its available resources too.
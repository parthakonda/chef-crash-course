# Understanding Attributes

Attribute - information/detail. What kind of information it is? It is the information related to the node. 

For example, 

I would like to know the information about my taget Operating System. Based on that I would like to install something in it.

Wait!

Before that who will provide this information and what time?

There is a process called `ohai` which collects the information about the node and sync's with the server. And this sits in the node.

## How to access this information in my cookbook/recipe?

You can access this information using node['platform'].

And what are other types of attributes available?

- platform
- platform_version
- ip_address
- macaddress
- fqdn
- hostname
- domains
- recipes
- roles
- ohai_time

## How can I define my own attributes? And where can I create them?
Attributes belongs to cookbooks. Create a folder called attributes inside your cookbook.
And create a file called default.rb - which is nothing but attribute file.

- Define required attributes/change the default attributes.
- Upload the cookbook

```
node.default['<attribute_name>'] = <value>
```

# How can I access these attributes in recipes?
You can use the defied attribute name recipe as `node['<attribute_name>']`


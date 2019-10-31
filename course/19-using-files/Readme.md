# Working with directories and files

## Use case

So far using chef we've successfully installed nginx. But we've not made the customization in the content.

# Create files
- Go inside the specific cookbook.
- knife generate file index.html

# Edit the created file with the desired content

# Upload
knife cookbook upload <cookbook>

# Creating files
```
file "<destination>" do
    action :create
end
```

# Copying files
```
cookbook_file "<destination>" do
    source "index.html"
    action :create
end
```

# Creating directory
```
directory '/etc/apache2' do
  owner 'root'
  group 'root'
  mode '0755'
  action :create
end
```

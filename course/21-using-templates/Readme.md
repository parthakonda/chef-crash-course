# Understanding chef templates

A cookbook template is an Embedded Ruby (ERB) template that is used to dynamically generate static text files.

Can contain

- expressions
- statements


# Use case
Create a file in node that depends on the input (dynamic). 
- Create file in home directory
- File name `welcome.txt`
- Content should be `Welcome <Mesasge>`
- Message: Dynamic and depends on the username

# Identify the resources
- file
- cookbook_file
- template

# Generating template
You need to go inside the cookbook

```
chef generate template <template_name>
```

# Accessing data
```
<%= @yourvariable %>
```

# Template resource

```
template "<destination_path>" do
  source "<source_template_file_name>"
  action :create

  variables <variable_name>: {
      # desired variables hash
  }
end
```

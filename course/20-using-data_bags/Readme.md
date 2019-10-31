# Using data bags

## What is data bag?
- Global variables accross the repo
- It is just a json file

## Creating data bag
```
knife data bag create <data_bag_name>
```

## Uploading content to data bag
```
knife data bag from file <data_bag_name> <json_file_locatio>
```

## Using data bag in cookbook
- Import the databag
```
<destination_variable> = data_bag_item('<databag_name>', '<file_name>')
```

- Using it in recipes
```
"#{destination_variable}"
```
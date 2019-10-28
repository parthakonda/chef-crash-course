# Chef generate commands

using `chef generate <module>` you can generate the following things.

`app` - which will creates the chef-repo and internal structure.
```
Syntax:
chef generate app <app_name>

Example:
chef generate app sample
```


`cookbook` - which will generate the cookbook inside of your chef repo cookbooks i.e., `chef-repo/cookbooks/<cookbook_name>`.

```
Syntax:
chef generate cookbook <cookbook_name>

Example:
chef generate cookbook sample
```

`template` - which will generate the templates inside your cookbooks.

```
Syntax:
chef generate template <template_name>
```

```
Example:
chef generate template hosts
```







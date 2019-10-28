# Understanding chef building blocks

## Understanding chef-repo folder structure

Generate the chef repo using `chef generate app <app_name>`. Initially chef will give you the following folders & files

Example:
```
chef generate app sample
```

The above command will generate the following

```
* sample
  * README.md
  * test
    * integration
      * default
        * default_test.rb
  * cookbooks
    * sample
      * recipes
        * default.rb
      * spec
        * spec_helper.rb
        * unit
          * recipes
            * default_spec.rb
      * Berksfile
      * chefignore
      * metadata.rb
```

`README.md` - Used to describe your app.

`cookbooks` - A folder/directory where it consists of your recipes, metadata about repo, dependacy list (Berksfile).

`recipes` - A directory by default consists of default.rc (default recipe).

`default.rb` - default recipe (when you're a trying to run a cookbook then this file/recipe will get execute).

`Berksfile` - berks is a dependacy manager for chef, and it will look for berkfile to get the list of dependancies for the repo.

`metadata.rb` - Meta data about the repo such name, description, maintainer and chef version.


`test` - This is to test your cookbooks using ruby spec.
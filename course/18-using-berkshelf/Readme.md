# Berkshelf

Berkshelf `berks` is a dependency manager where it will automatically download and upload all the internal dependencies with respect to the `Berksfile` configuration.

# Install Berks
By default it won't comes with chef. So we need to install by using ruby gem called `berks`.

- Create a file called `Gemfile` in your chef repo
  specify the following to add berks as dependency for our chef-repo
```
source 'https://rubygems.org'

gem 'berkshelf'
```

- And run `bundle install`
  This command will install the gem berkshelf for your chef repo.

# Managing dependencies through berksfile
Berksfile is with respective to the cookbook. So each cookbook will have its own berksfile.

- Default Berksfile configuration
`Berksfile`
```
# frozen_string_literal: true
source 'https://supermarket.chef.io'

metadata
```

- Add dependency

`Berksfile`

Syntax:
```
# frozen_string_literal: true
source 'https://supermarket.chef.io'

metadata
cookbook '<cookbook', '~> <version>'
```

Example:
```
# frozen_string_literal: true
source 'https://supermarket.chef.io'

metadata
cookbook 'nginx', '~> 10.0.2'
```


- Install using berks
```
berks install
```

- Upload using berks
```
berks upload
```

Note: You need to be in the same directory where your user.pem resides
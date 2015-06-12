Original repo: [andrewmp1/spree_api_extend](https://github.com/andrewmp1/spree_api_extend)

SpreeApiExtend
==============

A couple quick additional methods on the api to better support JS MVC frontends.

- Create users (non-admin): POST  /api/users  json: {"user": {"email": "spree@example.com", "password": "spree123"}}. Returns @user
- Login users: POST  /api/session  json: { "session": { "email": "email", "password": "password"}}. Returns @user
- Get current order & user: GET  /api/status
- Current user's orders: GET /api/orders. Returns @orders

CAUTION
------------
These modifications are changing the default spree authorization for the api that could introduce security issues.  Be sure you look through the changes before you do anything productiony!

Installation
------------

Add spree_api_extend to your Gemfile:

```ruby
gem 'spree_api_extend', github: 'Wangdi/spree_api_extend', branch: '3-0-stable'
```

Bundle your dependencies and run the installation generator:

```shell
bundle
bundle exec rails g spree_api_extend:install
```

Testing
-------

Be sure to bundle your dependencies and then create a dummy test app for the specs to run against.

```shell
bundle
bundle exec rake test_app
bundle exec rspec spec
```

When testing your applications integration with this extension you may use it's factories.
Simply add this require statement to your spec_helper:

```ruby
require 'spree_api_extend/factories'
```

Copyright (c) 2013 Drew Purdy, released under the New BSD License

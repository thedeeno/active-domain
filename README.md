# Active::Domain

## Motivation

Today, Rails makes the assumption that your business domain lives inside a web application. This assumption is awkward when you take a product-wide perspective; many tools need convenient access to a product's business logic but don't need the complexity of web concepts. Put another way, mixing web-application concepts with domain concepts often makes no sense. Despite, this is the default architecture of rails today. The `active-domain` gem family aims to alleviate this pain.

### Problem: A Concrete Use-Case

Suppose you want to write a single suite of acceptance tests for your entire product. These acceptance tests will verify your entire stack from web, mobile, and cli interfaces; to push, sms, and email notifications; to perhaps even logging and metrics collection. Running these tests often requires 4 steps:

1) Initialize the bottom of the stack (often the data-store(s))
2) Harness the interfaces under test
3) Exercise
4) Verify results via the above (or some other) interface

It's convenient to use your business domain to do #1 - the api is clean and services/factories can be leveraged for maximal productivity. Conversely, driving your API layer (or some other application) to do this setup is often painful. This application will have authentication, authorization, session, and access-pattern concerns that are completely irrelevant and frustrating to configure/workaround.

### Solution

Make it convenient for your domain to live outside your web/api application. If your domain lives outside your web/api application, you'll often fall-into creating the appropriate boundaries so you can easily drive it in a variety of contexts.

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'active-domain'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install active-domain

## Usage

TODO: Write usage instructions here

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake rspec` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/[USERNAME]/active-domain. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](contributor-covenant.org) code of conduct.


## License

The gem is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).


# Moesif Rails 4 Example with Rails

[Ruby Rack](http://rack.github.io/) is what most Ruby Web frameworks like Rails are built on top of.
[Rails](http://guides.rubyonrails.org/) is one of
the most popular frameworks.

[Moesif](https://www.moesif.com) is an API analytics and monitoring platform.
[moesif-rack](https://github.com/Moesif/moesif-rack)
is a middleware that makes integration with Moesif easy for Rack based
applications and frameworks, including Rails.

This example is a Rails web application with Moesif Rack integrated. Its based
on the [quick start tutorials of Rails](http://guides.rubyonrails.org/getting_started.html)
and this popular [blog post regarding RESTful APIs on Rails](https://blog.codelation.com/rails-restful-api-just-add-water/)

## Key changes

[moesif-rack's documentation](https://www.moesif.com/docs/server-integration/rack/) has detailed installation instructions and configuration options. Key changes to the base example to enable Moesif:

- Add `gem 'moesif_rack'` to the Gemfile
- Modify the `config/application.rb` to use your Moesif Application Id.

Your Moesif Application Id can be found in the [_Moesif Portal_](https://www.moesif.com/).
After signing up for a Moesif account, your Moesif Application Id will be displayed during the onboarding steps. 

You can always find your Moesif Application Id at any time by logging 
into the [_Moesif Portal_](https://www.moesif.com/), click on the top right menu,
and then clicking _Installation_.

## How to run

1. Verify Ruby and Rails versions is 2.3 and above via `ruby -v`
Verify Rails is 4.0 or higher via `rails --version`

3. Install all dependencies via `bundle install`

4. Be sure to edit the `config/application.rb` to change the application id to your real one obtained from Moesif.

```ruby
# config/application.rb
moesif_options = {
  'application_id' => 'Your application Id'
}
```

6. To run

```bash
bin/rails server
```

You may have to run `bin/rake db:migrate RAILS_ENV=development ` first to set up db.


7. To see a list of routes that you can run tests against run `rake routes`. Send some requests to the API routes and verify that the API calls are captured in your Moesif account.

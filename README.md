# This library is no longer being maintained. Use at your own risk #

# ClientSideValidations-Formtastic #

[![Build Status](https://secure.travis-ci.org/dockyard/client_side_validations-formtastic.png?branch=master)](http://travis-ci.org/dockyard/client_side_validations-formtastic)
[![Dependency Status](https://gemnasium.com/dockyard/client_side_validations-formtastic.png?travis)](https://gemnasium.com/dockyard/client_side_validations-formtastic)
[![Code Climate](https://codeclimate.com/badge.png)](https://codeclimate.com/github/dockyard/client_side_validations-formtastic)

[Formtastic](https://github.com/justinfrench/formtastic) plugin for [ClientSideValidations](https://github.com/bcardarella/client_side_validations)

## Installation ##

In your Gemfile add the following:

```ruby
gem 'formtastic'
gem 'client_side_validations'
gem 'client_side_validations-formtastic'
```

Order matters here. `Formtastic` and `ClientSideValidations` need to be
required **before** `ClientSideValidations-Formtastic`.

[Follow the remaining installation instructions for ClientSideValidations](https://github.com/bcardarella/client_side_validations/tree/3-2-stable/README.md)

Add the following line to `app/assets/javascripts/application.js`

```javascript
//= require rails.validations.formtastic
```

Again, order matters. You should add this line after the require for `rails.validations` as described in the `ClientSideValidations` installation instructions.

If the asset pipeline is disabled the asset file will be copied
into `public/javascripts` when the `ClientSideValidations` install generator is run.

At any time you can copy the asset file into your project by running:

```
rails g client_side_validations:copy_assets
```

If the asset pipeline is disabled the asset file will be copied
into `public/javascripts`. Otherwise the asset file will be copied into
`app/assets/javascripts` (or whatever asset directory you have
defined)

## Usage ##

The usage is the same as `ClientSideValidations`, just pass `:validate => true` to the form builder

```ruby
<%= semantic_form_for @book, :validate => true |book| do %>
  <%= book.input :name %>
<% end %>
```

Per-input options are done with `:validate`

```ruby
<%= book.input :name, :validate => { :presence => true, :uniqueness => false }
```

## Authors ##

[Brian Cardarella](http://twitter.com/bcardarella)

[We are very thankful for the many contributors](https://github.com/dockyard/client_side_validations-formtastic/graphs/contributors)

## Versioning ##

This gem follows [Semantic Versioning](http://semver.org)

Major and minor version numbers will follow `Rails`'s major and
minor version numbers. For example,
`client_side_validations-formtastic-2.2.0` will be compatible up to 
`~> formtastic-2.2.0`

## Want to help? ##

Please do! We are always looking to improve this gem. Please see our
[Contribution Guidelines](https://github.com/dockyard/client_side_validations-formtastic/blob/master/CONTRIBUTING.md)
on how to properly submit issues and pull requests.

## Legal ##

[DockYard](http://dockyard.com), LLC &copy; 2012

[@dockyard](http://twitter.com/dockyard)

[Licensed under the MIT license](http://www.opensource.org/licenses/mit-license.php)

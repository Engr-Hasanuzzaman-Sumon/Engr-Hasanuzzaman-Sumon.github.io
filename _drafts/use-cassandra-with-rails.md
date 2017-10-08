---
layout: post
title:  Guide for using cassandra with rails
categories: database
subcategory: Intermediate
---
**N.B I am assuming that you have install cassandra on your machine**
# integrate cassandra with rails
## Installation

Add it to your Gemfile:

    gem 'cequel'
If you use Rails 5, add this:

    gem 'activemodel-serializers-xml'
    Rails integration

Generate a default configuration file with:

    rails g cequel:configuration
Once you've got things configured (or decided to accept the defaults), run this to create your keyspace (database):

    rake cequel:keyspace:create
Setting up Models

Unlike in ActiveRecord, models declare their properties inline. We'll start with a simple Blog model:

    class Blog
      include Cequel::Record
    
      key :subdomain, :text
      column :name, :text
      column :description, :text
    end

Now run migration for this model using 
    rake cequel:migrate

# *************** DOES NOT WORK (ACTIVE RECORD METHODS)
- count

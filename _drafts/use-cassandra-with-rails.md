---
layout: post
title:  Guide for using cassandra with rails
categories: database
subcategory: Intermediate
---
# Install cassandra using following document 
(cassandra installation guide)[https://www.digitalocean.com/community/tutorials/how-to-install-cassandra-and-run-a-single-node-cluster-on-ubuntu-14-04]

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


# -------------- DATABASE DESIGN IN 
## Cassandra Data Model Rules
- Maximize the number of writes


---
layout: post
title:  "My Ruby Learning"
date:   2015-10-24 2:44:00
categories: ruby beginner
---

1. Using ruby metaprogramming always we can add instance variable & method to specific object.

    {% highlight ruby linenos%}
    # Example 2: create a new instance of class Object
    my_object = Object.new

    # create a second instance of class Object
    my_other_object = Object.new

    # define a method on my_object to set the instance variable @my_instance_variable
    def my_object.set_my_variable=(var)
      @my_instance_variable = var
    end

    # define a method on my_object to return value of instance variable @my_instance_variable
    def my_object.get_my_variable
      @my_instance_variable
    end

    my_object.set_my_variable = "Hello"
    my_object.get_my_variable # => Hello

    my_other_object.get_my_variable = "Hello" # => NoMethodError

    {% endhighlight %}
    
    <h4>Some rails quick info that will help you to think in new way</h4>
    <ol>
  <li>
        request.format return request format like :html, :json,...
        we can use this like 
        if request.format.symbol == :html
           .....
        else
            ......
        end    
  </li>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
</ol>

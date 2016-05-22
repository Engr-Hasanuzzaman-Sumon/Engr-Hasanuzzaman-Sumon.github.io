---
layout: post
title:  "My every day Learning"
date:   2015-10-24 2:44:00
categories: ruby beginner
tags: [ruby]
---

# Add method to object
Using ruby metaprogramming always we can add instance variable & method to specific object.

{% highlight ruby %}
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
    
# Rails info:
Some rails quick info that will help you to think in new way

* request.format
It return request format like `:html, :json, :pdf...`
we can use this like:

{% highlight ruby %}
if request.format.symbol == :html
   .....
else
    ......
end
{% endhighlight %}

* `foo = true and false #foo is true beacuse for assign = prioritty is greater then and `
* every ruby block and statement return value even class

{% highlight ruby %}
var = class Foo
  4
end
{% endhighlight %}

For above code the value of vae is 4 beacuse class declaretion return 4.

* An object is composed of a bunch of instance variables and a link
to a class.

* The methods of an object live in the object’s class (from the point
of view of the class, they’re called instance methods).

* The class itself is just an object of class Class. The name of the
class is just a constant.

* Class is a subclass of Module. A module is basically a package of
methods. In addition to that, a class can also be instantiated (with
new( )) or arranged in a hierarchy (through its superclass( )).

* Constants are arranged in a tree similar to a file system, where
the names of modules and classes play the part of directories and
regular constants play the part of files.

* Each class has an ancestors chain, beginning with the class itself
and going up to BasicObject.

* When you call a method, Ruby goes right into the class of the
receiver and then up the ancestors chain, until it either finds the
method or reaches the end of the chain.

* Every time a class includes a module, the module is inserted in
the ancestors chain right above the class itself.

* When you call a method, the receiver takes the role of self.

* When you’re defining a module (or a class), the module takes the
role of self.

* Instance variables are always assumed to be instance variables of
self.

* Any method called without an explicit receiver is assumed to be a
method of self. 

* [Ruby example intrview question with answer](https://github.com/gregstallings/ruby-trivia)

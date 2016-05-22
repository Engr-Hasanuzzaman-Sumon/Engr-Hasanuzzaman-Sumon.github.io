---
layout: post
title:  "Different way to declare class method to Ruby Class"
date:   2015-10-24 03:03:00
categories: ruby
subcategory: intermediate
---

## There are many ways to declare class method in ruby.

Most common way of declare class method is:

### Using most common `self`
{% highlight ruby linenos%}
class Foo
    def self.capitalize_name
      "My captalize name is #{name.upcase}"
    end
end

print MyClass.capitalize_name # => My captalize name is Foo
{% endhighlight %}

### In this method we use class name instead of `self`:
{% highlight ruby linenos%}
# approach 2
class Foo
  def Foo.capitalize_name
    "My captalize name is #{name.upcase}"
  end
end

print MyClass.capitalize_name # => My captalize name is Foo
{% endhighlight %}

### First declare class without method, then add method:
{% highlight ruby linenos%}
# approach 3
class Foo;end
# defining a class method out with the class definition
def Foo.capitalize_name
name.upcase
end

print MyClass.capitalize_name # => My captalize name is Foo
{% endhighlight %}

### First declare class without method, then add method:
{% highlight ruby linenos%}
# approach 4
# define a new class named MyClass
# here we can see that our declare class just object of Class
Foo = Class.new
# add the capitalize_name to MyClass
def Foo.capitalize_name
name.upcase
end

print MyClass.capitalize_name # => My captalize name is Foo
{% endhighlight %}

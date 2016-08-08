---
layout: post
title:  "Ruy interview preparetion"
date:   2016-06-07
categories: ruby
subcategory: advance
---

# Class
- what is class?
- how differ from object?
- what is class access control?
    Public methods enforce no access control -- they can be called in any scope.
    Protected methods are only accessible to other objects of the same class.
    Private methods are only accessible within the context of the current object.

 ## Classes hold data, have methods that interact with that data, and are used to instantiate objects.
 ```ruby
 class Foo
 # do some thing
 end
 ```
     Public methods enforce no access control -- they can be called in any scope.
 Protected methods are only accessible to other objects of the same class.
 Private methods are only accessible within the context of the current object.

## Many ways to call method in ruby
```ruy
#Method 1:
s = SomeObject.new
method = s.method(:dynamic_method)
method.call

# Method 2:
s = SomeObject.new
s.send(:dynamic_method)

# Method 3:
s = SomeObject.new
eval "s.dynamic_method"

# Method 4:
s = SomeObject.new
s.dynamic_method

```
# Module
 - what is module?
 - what happen if we `extend` module in class?
 - what happen if we `include` module in class?
 - how we can use method with in module?
     - ex
     ```ruby 
       Module Foo
          def name
            'sumon'
          end

          def call_name
            name
          end
        end
     ```
 - what happen if instance extend module?
       `Foo.new.extend(Module)`
 - what is `require` ?
 - what is `load` ?
 - wiht is different between `require` and `load` ?
 - 


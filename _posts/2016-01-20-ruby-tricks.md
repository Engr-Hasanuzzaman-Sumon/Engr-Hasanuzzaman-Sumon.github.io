---
layout: post
title:  "Ruby tricks"
date:   2016-01-20
categories: ruby
subcategory: intermediate
---

## Different ways to call a lambda
{% highlight ruby linenos%}
my_lambda = -> { puts 'Hello' }
my_lambda.call
my_lambda[]
my_lambda.()
my_lambda.===
{% endhighlight %}

## Creating a pre-filled array
The Array class can take an argument + a block, which let’s you create an array with n elements.
By default these elements are nil, but if you have a block, the values will come from it.

Example:
    `Array.new(10) { rand 300 }`This will generate an array with 10 random numbers which are between 0 and 300.</p>

## Convert any value into a boolean
{% highlight ruby linenos%}
!!(1)   # true
!!(nil) # false
{% endhighlight %}

[referece](http://www.blackbytes.info/2016/01/ruby-tricks/)

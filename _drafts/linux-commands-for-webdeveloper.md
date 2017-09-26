---
layout: post
title:  "Algorithms learning"
date:   2016-08-7
categories: Algorithms
subcategory: intermediate
---

# Close hanged Rubymine
## Find Rubymine process id
  ps -aux | grep Rubymine
  
## Kill rubymine process
  `sudo kill -9 found_id`
## If port 3000 still show used then use below command to close that
  ``sudo kill `sudo lsof -t -i:3000```
  
If that doesn't work you could also use `$()` for command interpolation:
  `sudo kill $(sudo lsof -t -i:9001)`

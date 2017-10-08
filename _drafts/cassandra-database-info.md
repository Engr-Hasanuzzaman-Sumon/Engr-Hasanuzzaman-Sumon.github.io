---
layout: post
title:  Guide for using cassandra with rails
categories: database
subcategory: Intermediate
---
# Install cassandra using following document 
(cassandra installation guide)[https://www.digitalocean.com/community/tutorials/how-to-install-cassandra-and-run-a-single-node-cluster-on-ubuntu-14-04]


# General information about cassandra
- It’s an inherent part of Cassandra’s replica design that all data for a single
  row must fit on a single machine in the cluster. The reason for this
  limitation is that rows have an associated row key, which is used to
  determine the nodes that will act as replicas for that row. Further, the
  value of a single column cannot exceed 2GB. Keep these things in mind
  as you design your data model.
  
-  

# -------------- DATABASE DESIGN IN 
## Cassandra Data Model Rules
- Maximize the number of writes


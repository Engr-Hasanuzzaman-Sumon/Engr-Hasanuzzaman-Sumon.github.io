---
layout: post
title:  Guide for using cassandra with rails
categories: database
subcategory: Intermediate
---
# Install cassandra using following document 
[cassandra installation guide](https://www.digitalocean.com/community/tutorials/how-to-install-cassandra-and-run-a-single-node-cluster-on-ubuntu-14-04)


# General information about cassandra
- It’s an inherent part of Cassandra’s replica design that all data for a single
  row must fit on a single machine in the cluster. The reason for this
  limitation is that rows have an associated row key, which is used to
  determine the nodes that will act as replicas for that row. Further, the
  value of a single column cannot exceed 2GB. Keep these things in mind
  as you design your data model.
  
- Cassandra create separate db for each column family.
  `/var/lib/cassandra/data` contain all the key-spaces. Under every key-spaces  there are different folders for
  different column family. We can use [`sstabledump`](https://docs.datastax.com/en/cassandra/3.0/cassandra/tools/ToolsSSTabledump.html) tool for reading row `sstable` data.
  `sudo apt-get install cassandra-tools` will install `sstabledump` 
# -------------- DATABASE DESIGN IN 
## Cassandra Data Model Rules
- Maximize the number of writes

# Application design in cassandra
- In Cassandra you don’t start with the data model; you start with the query
  model. ( what kind of query you will perform on data)
-   


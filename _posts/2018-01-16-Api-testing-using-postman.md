---
layout: post
title:  API testing using Postman
date:   2018-01-16
categories: testing
subcategory: Intermediate
---
All most every web developer or web tester are familiar with [Postman](https://www.getpostman.com/){:target="_blank"}{:target="_blank"}.
Postman is a Chrome add-on and Mac application which is used to fire requests to an API.
It is very lightweight, fast and easy to use. Using this tool we can make different kinds of HTTP requests – ``` GET, POST, PUT, PATCH and DELETE ```.

In this post, I am going to show some of features of *Postman* that I am using in my everday life.

1. **Collection:**
  A Postman Collection lets you group individual requests together. You can organize these requests in folders.
  For every projct I create new collection.
  
    You can create a new collection from the:

    - Sidebar
    - New button
  
    **Create collection from ```Sidebar```**

    In the sidebar, select “*Collections*” and click the “*Collections*” icon.
      [add new collection from sidebar screenshort](https://s3.amazonaws.com/postman-static-getpostman-com/postman-docs/collections_icon1.png){:target="_blank"}
    CREATE A NEW COLLECTION modal will appear than fill the require information.
      [create collection modal screenshort](https://s3.amazonaws.com/postman-static-getpostman-com/postman-docs/collections-createcollectionmodal.png){:target="_blank"}
    
    **Create collection from ```New``` button**

    In the header toolbar, click the New button.
      [New button screenshort](https://s3.amazonaws.com/postman-static-getpostman-com/postman-docs/HeaderToolBar.png){:target="_blank"}
      
    The Create New tab appears than select *Collection* and fill require information.
    
    For more information you can check 
    [Offical documentation of Collection](https://www.getpostman.com/docs/postman/collections/creating_collections#collapse-category-0-2){:target="_blank"}
  
2. **Folder:**
  Folders are a way to organize your API endpoints within a collection into intuitive and logical groups to mirror your workflow. I create different folder for every small logical section of my app (most of the time for every Controller).
  For example, ***dashboard***,***profile*** etc
  [Add Folder Dropdown screenshort](https://s3.amazonaws.com/postman-static-getpostman-com/postman-docs/addFolderDropdown.png){:target="_blank"}

3. **Sharing collections:**
  This is the feature that I like most. Using this feature you can share your collection to your teammate.
  You must be signed in to your [Postman account](https://www.getpostman.com/docs/postman/launching_postman/postman_account){:target="_blank"}    to upload or share a collection
  [Share Collection Dropdown screenshort](https://s3.amazonaws.com/postman-static-getpostman-com/postman-docs/shareCollectionDropdown.png){:target="_blank"}

There are three options for sharing collections.
  - [Team Sharing only for Postman Pro user](https://s3.amazonaws.com/postman-static-getpostman-com/postman-docs/59137211.png){:target="_blank"}
  - [Collection link](https://s3.amazonaws.com/postman-static-getpostman-com/postman-docs/58564829.png){:target="_blank"}
  - [Embed button](https://s3.amazonaws.com/postman-static-getpostman-com/postman-docs/58564746.png){:target="_blank"}

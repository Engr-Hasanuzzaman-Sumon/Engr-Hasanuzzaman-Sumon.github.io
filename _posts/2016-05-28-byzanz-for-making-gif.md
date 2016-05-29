---
layout: post
title:  "Make gif format screen cast using byzanz"
categories: screen cast making
tags: [screen cast]
comments: true
disqus_url:
disqus_identifier: byzanz1
---

# `byzanz`
It is the software for making screen cast in *gif* format for linux system

## Installation
 * for ubuntu 11.10 to 13.10
  `sudo add-apt-repository ppa:fossfreedom/byzanz`
  `sudo apt-get update && sudo apt-get install byzanz`

 * for ubuntu 14.04 and above
   `sudo add-apt-repository ppa:fossfreedom/byzanz`
   `sudo apt-get update && sudo apt-get install byzanz`

## Usage
  `byzanz` has no GUI. We have to use terminal for using it.
   Below I have showed simple example of how we can use it.
   `byzanz-record --duration=15 --x=200 --y=300 --width=700 --height=400 foo.gif`

   The above command will record your screen for 15 sec and save it as foo.gif. Of course you can
   change output directory by following
   `byzanz-record --duration=15 --x=200 --y=300 --width=700 --height=400 ~/foo.gif`
   above command will record your screen for 15 second and save it to your ubuntu home directory.


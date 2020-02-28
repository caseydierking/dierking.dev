---
title: Python Mutable Types
date: "2020-02-28T22:40:32.169Z"
template: "post"
draft: true
slug: "/posts/python-mutable-types/"
category: "Learnings"
tags:
  - "Python"
description: "My experience with python mutable types."
socialImage: "/media/mutable.png"
---
I've always dabbled in python a little bit. I would play with it here or there to do very simple tasks. Recently though, I had a project come up where I had the opportunity to choose the right tool for the job. In this case, the right tool was python. 

This particular project required a python script that would run on a raspberry pi device and listen for inputs via the GPIO pins. I will probably write about this project when it is all finished, so I'll only leave you with that little teaser for now. 

I implemented the bare minimum requirements for this project to be successful. Launch a python script....listen for input....do something with the input. In my case, I was hitting an API and posting data to the server. I had to account for one thing though... What if the internet connection dropped? 

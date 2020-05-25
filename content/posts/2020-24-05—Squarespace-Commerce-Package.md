---
title: Squarespace Commerce Package
date: "2020-05-24T22:40:32.169Z"
template: "post"
draft: false
slug: "/posts/Squarespace-Commerce-Package/"
category: "Projects"
tags:
  - "Python"
description: "A python module that provides easy access to Squarespace's Commerce API"
socialImage: "/media/pypi.png"
---
On May 20, 2020 I published my very first package to the [Python Package Index](https://pypi.org/) and made it available for the world to use. I'm proud and excited to share this milestone.

I recently wrote a simple python application for my wife that utilizied the Squarespace Commerce API. During the development of that project, I was surprised to learn that there were no existing modules out there (that had been maintained) that abstracted the api and made it easy to query. Once I had the application built for my wife, I realized I could take what I learned and turn it into something that could be useful for anyone. And since there were was nothing exsting, I decided to write my own and publish it. 


Introducing **Squarespace-Commerce**

You can can acces it on [PyPi](https://pypi.org/project/squarespace-commerce/) or view the [Github source.](https://github.com/caseydierking/squarespace-commerce-python) Future plans include expanding the library to use the Transactions and Inventory APIs. 

Here is how to use it:

### Usage

````python
#Import the module
from squarespace_commerce import Squarespace
````

````python
#Create a squarespace class.
order = Squarespace('APIKEY')

#Optional Parameters include:
#APIVersion defaults to 1.0
order = Squarespace('APIKEY','APIVERSION','APIBASEURL')
````


### Orders API

````python
#Get the first page of orders, returns 50:
order.get_orders()

#Optional Parameters include:
order.get_orders(cursor='{Token}',modified_after='{ISO 8601 Date}'',modified_before='{ISO 8601 Date}',fulfillment_status='{PENDING | FULFILLED | CANCELLED}')

#Get a specific order
order.get_order('order_id')

#Fulfill a specific order
order.fulfill_order('order_id')

#Optional Parameters include:
order.fulfill_order('order_id', send_notification={True | FALSE}, ship_date={ISO 8601 Date}, tracking_number='',
                      carrier_name='', service='', tracking_url='{valid_url}'):
````
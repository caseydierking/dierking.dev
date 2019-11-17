---
title: Proxy an IIS hosted application
date: "2019-11-16T22:40:32.169Z"
template: "post"
slug: "/posts/access-iis-hosted-application-from-mobile-device/"
category: "Tutorials"
tags:
  - "IIS"
  - ".NET"
  - "Tips"
description: "Make a locally hosted application available to anyone on your network."
socialImage: "/media/iisexpress.png"
---

![IISExpress](/media/iisexpress.png)


Recently, I ran into a situation where I needed to access my .NET application from my mobile device on my local network. In the past, I've used the very excellent [Ngrok](ngrok.com) to do this with a rails application. When I tried it for my .NET application which is served up via IIS, I only ran into errors. 

This is because IIS natively only serves up websites to clients that are bound to localhost. Essentialy, I can only access my localhost application from.... my localhost.

Rather than fussing with all the settings with enabling remote connections, there is an amazing utility out there called [IISExpress-Proxy](https://github.com/icflorescu/iisexpress-proxy). Here is how to get up and running with it:

## Install IISExpress-Proxy

Make sure you have [https://nodejs.org/en/](https://nodejs.org/en/) installed. Then install the plugin.
> npm install -g iisexpress-proxy

After that, you just have to run the plugin. Running it in Git bash did not work for me. I had to actually run this in the command prompt. *

> iisexpress-proxy localPort to proxyPort

For example, if your application port is **49558** and you want to proxy that port to **3000** it would look like this:

> iisexpress-proxy 49558 to 3000

At this point, your website is avaialble via the ip address of your machine with the port. IISExpress-Proxy will give you what your current machine's local ip address is. ex. 192.168.1.25:3000. This will allow you to connect to your application from any device on the same network as your development machine. 

**Bonus Points:** If you want to then serve this application over the internet and allow someone to access it, you can then use nGrok and point it to the proxied port.
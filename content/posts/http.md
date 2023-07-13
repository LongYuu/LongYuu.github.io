---
title: "Http"
subtitle: ""
date: 2023-07-04T14:24:25+09:00
draft: false
author: Yu Long
categories: ["Web"]
tags: [""]
featuredImage: "/images/http/http-1.png"
featuredImagePreview: "/images/http/https_http.png"
hiddenFromHomePage: false
hiddenFromSearch: false
---
HTTP and HTTPS are widely used for deliverying various contents on the web. But do you know some advanced features of them? 

<!--more-->
## 1 HTTP {#http}
HTTP, Hyper Text Transfer Protocol, is an application layer protocol based that is sent over TCP.
Since HTTP is stateless, it can use cookie and session to manage the state, such as user login information. 

cookie is a plain text sent by Server to Client, and saved by Client. When request the same website the browser will send it to Server for checking. 
session is created and stored by Server, and Server can recognize it based on the **JSESSIONID**. But if cookie is prohibited by browser, **JSESSIONID** can be returned by URL rewrite. 

### Access control (CORS)
CORS, Cross-Origin Resource Sharing, is an HTTP-header based mechanism that allows server to indicate any origins other than its own from which a browser should permit loading resources. 
{{<image src="/images/http/cors_principle.png" caption="" title="" class="" src_s="" src_l="" height="" width="" linked="" rel="">}}
{{<image src="/images/http/simple_req.png" caption="" title="" class="" src_s="" src_l="" height="" width="" linked="" rel="">}}

### Authentication 
HTTP provides a genere framework for access control and authentication, which can be used by server to challenge a client request, and by client to provide authentication information. 
{{<image src="/images/http/simple_req2.png" caption="" title="" class="" src_s="" src_l="" height="" width="" linked="" rel="">}}
When it comes to client side to ask user, usually a client will present a password prompt and then issue the request including the correct **Authorization** header

## 2 HTTPS {#https}
Added SSL/TLS to HTTP to make the data transfer more secure. 

{{<image src="/images/http/diff.webp" caption="" title="" class="" src_s="" src_l="" height="" width="" linked="" rel="">}}

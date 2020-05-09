+++
title = "HMAC Implementation in JAVA"
date = 2020-05-04T17:40:32+05:30
images = []
tags = []
categories = []
draft = true
+++


This blog post detailed how to sign a message with HMAC to enable efficient and secure authentication. This is an additional layer of security over HTTPS. Some times there would be a situation to track the usage of the APIs for each client/customer. HMAC authentication module in your codebase signing your request message with a shared secret, so that server can verify the same at their end.

> HMAC is **H**ash-based **M**essage **A**uthentication **C**ode (Hashed MAC). HMAC is calculated as signature = HMAC("Message", secret, digest-algorithm)

HMAC authentication comprises the following steps

 1. The server needs to generate a shared secret with clientID and share the same clientID and secret with the client application. Each client application will have a different secret.
 2. Construct request message to be signed(eg- "request body"|"HTTP MEthod"|ClientID|timestamp)
 3. The client generate HMAC value(signature) using the shared secret. Send out the request body to the Server with signature and client identifier(eg:- clientID or code) that uniquely identifies the client on the server-side.
4. Server extract HMCA value and client identifier to map shared secret from the request  
5. Construct request message as client constructed the message to be signed
6. Calculate the HMAC value using shared secrets and matches with HMAC value extracted from the request. If HMAC values matches, this means that message integrity is proved and respond to the request

```

```

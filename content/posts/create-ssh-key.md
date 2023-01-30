---
title: "How to generate a ssh-key"
subtitle: "The quick version"
date: 2023-01-30T08:00:00+08:00
lastmod: 2020-01-30T08:00:00+08:00
draft: true
author: "Josh Adams"
authorLink: ""
description: "A step by step guide on how to generate a ssh-key"
license: ""
images: []

tags: ["ssh-key"]
categories: ["tutorial"]

featuredImage : "/images/featured-image-ssh-key.jpg"
featuredImagePreview: ""

hiddenFromHomePage: false
hiddenFromSearch: false
twemoji: false
lightgallery: true
ruby: true
fraction: true
fontawesome: true
linkToMarkdown: true
rssFullText: false

toc:
  enable: true
  auto: true
code:
  copy: true
  maxShownLines: 50
math:
  enable: false
  # ...
mapbox:
  # ...
share:
  enable: true
  # ...
comment:
  enable: true
  # ...
library:
  css:
    # someCSS = "some.css"
    # located in "assets/"
    # Or
    # someCSS = "https://cdn.example.com/some.css"
  js:
    # someJS = "some.js"
    # located in "assets/"
    # Or
    # someJS = "https://cdn.example.com/some.js"
seo:
  images: []
  # ...
---
# Creating an SSH key using Windows:

## 1. Open a terminal window. 
To do this, press `Windows + R and type "cmd"`.

## 2. Generate an SSH key pair. 
To generate an SSH key pair, type:
 ```
 ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
 ```
 
 *Optional:* Enter a passphrase when prompted. By default your private key will be stored unencrypted on your local machine; This is not ideal. Keep in mind, if you do create a passphrase, you will be prompted for it during each use unless you utilize a tool to do so.

## 3. Save the SSH key pair. 
Copy and paste the contents of the file `id_rsa.pub` into a text editor and save it as a text file.
```
%UserProfile%\.ssh\id_rsa.pub
```
This will output your public key. Copy this key to be used.

## 4. Copy the public key to the remote server. 
To do this, use the command 
```
ssh-copy-id -i path/to/public_key user@hostname”
```
The command will prompt you for your password.

## 5. Test the connection. 
To test the connection, type `ssh user@hostname`. If everything is set up correctly, you should be logged in without being prompted for a password.

Congratulations! You have successfully created an SSH key pair and copied it to the remote server.

# Creating an SSH key using Mac:
Creating an SSH Key Using Mac

## 1. Open the terminal application.
## 2. Terminal
Enter the command `ssh-keygen -t rsa` and press enter.
## 3. Save Location
You will be asked to enter a file in which to save the key. Press enter to accept the default.
## 4. Passphrase
You will be asked to enter a passphrase. This is an optional security measure that can be used to protect the key. You can leave this blank or enter a passphrase.
## 5. Generation
The key will be generated and stored in the file that you specified.
## 6. Viewing the key
To view the key, enter the command `cat <filename>`, where <filename> is the name of the file that you specified in step 3.
## 7. Copying the key
To copy the key to the clipboard, enter the command `pbcopy < <filename>`, where <filename> is the name of the file that you specified in step 3.
## 8. Success
You can now use the key to authenticate with remote servers.
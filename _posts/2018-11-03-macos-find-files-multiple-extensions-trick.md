---
layout: post
title:  "MacOS - Find all video, audio, CSVs, text files and copy it to other directories for backup etc"
date:   2018-10-27
desc: "MacOS - Find all video, audio, CSVs, text files and copy it to other directories for backup etc"
keywords: "Linux, Shell, DevOps, MacOS"
categories: [Devops]
tags: [Linux, Shell, DevOps, MacOS]
icon: icon-fire-alt
---

## You don't need to go to Finder, lookout for each & then copy paste.


### You can either copy all of them at once using below find command with regex incorporating with `rsync` or `cp` - 


- Using `rsync` - 

  `find -E . -regex '.*\.(jpg|png|mp4|mp3|csv|txt)' -exec rsync -avzh {} ~/found/ \;`

- Using `cp` - 

  `mkdir ~/found`

  `find -E . -regex '.*\.(jpg|png|mp4|mp3|csv|txt)' -exec cp {} ~/found/ \;`


### You can also copy them to individual directories - 


#### Copy all MP4 files to `videos` directory -


- Using `rsync` -

  `find -E . -regex '.*\.(mp4)' -exec rsync -avzh {} ~/found/videos/ \;`

- Using `cp` -

  `mkdir ~/found`

  `find -E . -regex '.*\.(mp4)' -exec cp {} ~/found/videos/ \;`


#### Copy all image files to `images` directory -

- Using `rsync` -

  `find -E . -regex '.*\.(jpg|png|jpeg)' -exec rsync -avzh {} ~/found/images/ \;`

- Using `cp` -

  `mkdir ~/found`

  `find -E . -regex '.*\.(jpg|png|jpeg)' -exec cp {} ~/found/images/ \;`



> **Note:** We can create simple shell script and put it as a cronjob, using rsync you can perform inremental backup of your data to another drive or folder. 

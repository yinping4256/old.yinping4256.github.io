---
layout: post
title: Let visual studio work with github
excerpt: ""
modified: 2015-04-27
tags: [tech]
comments: true
category: en
image:
  feature: 
  credit: 
  creditlink: 
---
I have been using UCSD git for programming CSE 160 assignments.

I like using IDEs for programming. Visual studio is my favorite. To save time, I have decided to write down steps I have used to make 
my visual studio 2013 work well with a third party git, which is UCSD Git in my case. Github is very similar.

In our course, we are given some startup codes in a remote UCSD git repository.

Here is what I have done:

1. Locally create a new empty project, without checking the "initial git" option in the wizard. 

2. Click `team` in the menu, choose "connect to team foundation server".  This opens a "Team Explorer". I usually put it on the right side.

3. Look for "Local Git Repositories". You can see a `clone` button right below it. Click it.

4. It prompts you to enter the URL of your repository. Use the "http" address of your repository. 

5. Choose the location where you will put your repository. I set it to my project folder. Then click `clone`.

6. Finally, mannually add files to current empty project. 


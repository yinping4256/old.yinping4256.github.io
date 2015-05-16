---
layout: post
title: "Using Git in Visual Studio 2013 in CSE 160 UCSD"
modified:
categories: en
excerpt:
tags: []
image:
  feature:
date: 2015-05-16T00:16:55-07:00
---
In CSE 160 I was forced to use git.ucsd.edu to submit my codes. The initial codes were given to run in Bang. However, debugging multithreading in linux is frustrating. So, I made the codes compatible with Visual Studio 2013. 

Then the problem became that, using Git in Windows appeared to be not as graceful as it is in Linux. 

First, if you prefer graphic git interface, for example, Github Client windows application, you will find it is not compatible with the school git service git.ucsd.edu. 

Second, if you prefer commindlines, you will have to install another git package "git for windows" from (https://msysgit.github.io/). The git instructions turned out to be much slower than it was in linux environment. 

So do we have a better solution? Definitely.

It turns out that Visual Studio 2013 has Git inside it. A good resouce for learning this is from pluralsight (http://www.pluralsight.com/courses/git-visual-studio-developers). Just watch the third part(Working With Visual Studio) and the fourth part (TFS 2013) is enough. Demos are extremenly clear.

To be concise, to use Visual Studio 2013 and let Git connect to a third party Git server, eg, git.ucsd.edu, we can follow these steps:

1. Create the project repository remotely on your Git server, eg, git.ucsd.edu. 

2. Copy the "https" address of your repository. ![图像超链接](//yinping4256.github.io/images/2015-05-16 00.35.15.png)

3. Open Visual Studio 2013. Create a new project(UNchecking "using git source control"), save it to any place you like. 

4. In VS2013 menu bar, click Team -> connect Teamserver. This opens a "Team Explorer" tab. On the tab, you can find "clone" button. Use the clone button and https address to clone from the remote git repository.

5. This will only clone the "master" branch. If you have another branch remotely, just look for "branch" in the tab, choose "new", from the pull-down menu, choose "origin/anotherBranch". VS2013 will use the same branch name as the new local branch name.

6. Add the files to your local project.

7. Sometimes you need special git instrucions, eg, git stash. You can't find it on the Team tab. Then go to TOOLS -> NuGet Package Manager -> Package Manager Console. You can type any git instructions there, given that "git for windows" is installed.

8. Note: the paths of your repository and project are different by default. I maintained them in this way: I don't care project files location, but I do care my codes. However, my codes are always synced with remote by using "Team Explorer".


# Hi Git, I'm ABAPer how do you do?

When there was a call for community sessions before #SAPtd I jumped on the opportunity to present on two topics that I feel were going to be under-represented at the event.

1. Developer Communication Skills
2. Git

So I proposed two abstracts to the community talk selection committee and they told me that they while they were very excited about both topics they could only take one and they would take the first one. Well I was excited, but to be honest,  also a little dissapointed. As much as I wanted to talk on communication skills for developers I really wanted to introduce ABAPers to Git as a method of source code control as I know it will become very important as we move toward the HCP and OpenUI5.

As we got closer to the conference I was advised that one of other speakers that was selected had to withdraw and I was asked to prepare my second talk.

This presentation was only delivered at #SAPtd in Las Vegas so all the people going to Berlin will miss out. For this reason and that there should be a bit of an intro to Git here on SCN. I thought I would distill my off the cuff talk into a short blog for the benefit of the ABAPers in the universe.

# Welcome to Source Control

So source control is not a new subject to ABAPers. We are used to putting our code into transport requests, which then enables the code to be delivered across the landscape and into production in an orderly manner.

Let's for a moment think about what happens when you put a code artifact into a transport request. It's not that hard. You lock the object so that you and only you can work on the object at one time. Until you release your transport, everyone else is prevented from doing anything to that object.

This is all well and good, but what happens in the following scenario?

1. You are working on a new feature request.
2. A bug is discovered in production that related directly to your code object.

Well resolving the bug will obviously trump the new feature but you are halfway though your change and it will need to be parked while the emergency is dealt with.

The challenge is you change request might have a whole bunch of other objects that are not ready to go to prod, let alone ready for regression testing.

So mostly you do something like the following:

1. Copy all of your changes to notepad* and save the file for safekeeping.
2. Hack the lock on the transport request and remove your file from your transport request
3. Copy the code from the prior transport (or back from production if they are different)
4. Open a new transport request. 
5. Make the hotfix.
6. Release the new transport. 
7. Add your object back into the old request and merge your changes in from the file you saved.
8. When you are ready you release the transport.

While this is functional and it is not the best. Also note that only one person can be working on each file at once.

# Enter Git

So what's so great about Git. Well, for starters the file types involved in a OpenUI5 project don't have to be edited in SE80. In fact you can set up your system to work on your project locally on your machine and there are many great blogs here on SCN to help you with that. This means that you can work on your project on the move rather that having to be connected to the ABAP app server in the same way you need to in the ABAP world.

Rather like I am doing right now :

```

	07:42:07 {master} ~/squarecloud/talks-and-blogs/blogs$ git commit -m 'Update Git Blog'
	[master e427b77] Update Git Blog
	 1 file changed, 56 insertions(+)
	 create mode 100644 sap/Hi Git I'm ABAPer how do you do.md

```

(Alright, alright don't get ahead of yourself Nigel, most of these good readers have no idea what you are on about)

# Back to the start.

So Git is a distributed source code control system where pretty much everything happens locally and you are only need a network connection when you are pushing to the remote server.

You don't even need to have a remote system to use Git. You can install git on your Linux, Mac or Windows system and use it to version whatever files you like without ever sharing your code. Personally I have done this when I was working on a project even though I wasn't working with other team members. This enabled me to version code and rollback changes if they didn't work.

For most scenarios though, you will need a remote system that all members of your team can access. For this, GitHub is the answer to your needs. Is it the only answer? No, there are others but it is a great place to start.

So surf on over to GitHub and signup for an account. 

(insert image of GitHub initial screen)

There are several options to consume GitHub content. Native apps, command line and the GitHub site itself. I will focus on the command line in this blog because  even though the native GUI applications simplify everything so nicely, sometimes the power that the command line affords is the only way to get out of the muddle. So I like to build up the muscle memory in my fingers so that when it hits the fan and my colleague's Windows commit has clobbered my commit I can recover without getting into a "tissie".

# First the init

Let's assume that we will start locally, because you are on a long haul flight (with power) and have had a great new idea you want to code or write about.
Lets call it NextBigThing.

The first thing you are going to do is to initialise a folder to be tracked under source control.

As I said we will start with the command line and look at other options later:

```

	05:56:24 ~/squarecloud$ mkdir NextBigThing
	05:56:39 ~/squarecloud$ cd NextBigThing/
	05:56:43 ~/squarecloud/NextBigThing$ git init
	Initialized empty Git repository in /home/nigeljames/squarecloud/NextBigThing/.git/
	05:56:46 (master) ~/squarecloud/NextBigThing$ 


```

So here we have created a new directory for our new exiting project and initialised it so that git can track its contents

Next we will start editing our documents and or code. I will start by creating a ProjectOverview.md to get my ideas down.

After editing that document for a while I need to see what is going on. I hit enter back on the command line.

	05:56:46 (master) ~/squarecloud/NextBigThing$ subl ProjectOverview.md
	06:05:58 (master) ~/squarecloud/NextBigThing$ 
	06:08:00 {master} ~/squarecloud/NextBigThing$ 


It is subtle in black and white but my command line prompt has changed from being round brackets and green to red curly brackets. This is my visual cue that my tracking is not up to date.

So let's see what is going on:

	06:08:00 {master} ~/squarecloud/NextBigThing$ ll
	total 16
	drwxrwxr-x  3 nigeljames nigeljames 4096 Nov 13 18:07 ./
	drwxrwxr-x 18 nigeljames nigeljames 4096 Nov 13 17:56 ../
	drwxrwxr-x  7 nigeljames nigeljames 4096 Nov 13 18:08 .git/
	-rw-rw-r--  1 nigeljames nigeljames  231 Nov 13 18:07 ProjectOverview.md
	06:12:01 {master} ~/squarecloud/NextBigThing$ git status
	On branch master

	Initial commit

	Untracked files:
	  (use "git add <file>..." to include in what will be committed)

		ProjectOverview.md

	nothing added to commit but untracked files present (use "git add" to track)
	06:12:09 {master} ~/squarecloud/NextBigThing$ 

So looking at the directory listing I can see my new file and by checking git's status I can see that I have one untracked file.

Git is nice and tells us what to do most of the time. It is telling me to add the file to be tracked. So let's do that:

	06:12:09 {master} ~/squarecloud/NextBigThing$ git add ProjectOverview.md 
	06:14:10 {master} ~/squarecloud/NextBigThing$ git status
	On branch master

	Initial commit

	Changes to be committed:
	  (use "git rm --cached <file>..." to unstage)

		new file:   ProjectOverview.md

It is now telling me that the tracked file needs to be committed. You can think of commiting to like saving a file. It is a snapshot of our file at that point in time.

So let's go ahead and commit the file:


	06:14:16 {master} ~/squarecloud/NextBigThing$ git commit -m "Initial brainstorming for the NextBigThing"
	[master (root-commit) 4ec926f] Initial brainstorming for the NextBigThing
	 1 file changed, 5 insertions(+)
	 create mode 100644 ProjectOverview.md
	06:18:00 (master) ~/squarecloud/NextBigThing$ 


Did you notice that the brackets have now changed back to curly?

This work-add-commit loop is what you will do most with git. 

# Share and share a like

We now need to share this idea with our stakeholders and team so we are going to create a repository on GitHub and then push our work there for all to see.

So we log onto GitHub and find the big green 'Add Repository' button. Personally, I love green for postive actions. 


(image)


We have to fill out the Repository name which has to be unique under your account. We enter a description and decide if we are making this public or private. I want the world to know about my new idea so of course we are making this public.

There are a couple of other options:

1. Initialize with a README
2. Add .gitignore
3. Add a licence

As we have content for our repository already we are going to leave these blank but if you were creating a repo from scratch on the GitHub site it would be pretty handy to choose these options.

A README.md is created if you select option one. This is a handy place to tell the world about your repo as it is displayed by default on the GitHub site.

The .gitignore file tells git which files to ignore when committing your code. This is handy if your IDE creates project files or there are secure files that are not appropriate to be shared publicly.

Lastly the licence is a handy feature for open source project that needs to have a licence to be considered open source.

So, with all that out of the way, we press another Big Green Button and create our project.

Git now presents us with options as to how to clone or push our repo.

Since we have content allready we are going to push our repo. 


	06:18:00 (master) ~/squarecloud/NextBigThing$ git remote add origin git@njames.github.com:njames/NextBigThing.git
	10:09:57 (master) ~/squarecloud/NextBigThing$ git push -u origin master
	Counting objects: 3, done.
	Delta compression using up to 8 threads.
	Compressing objects: 100% (2/2), done.
	Writing objects: 100% (3/3), 414 bytes | 0 bytes/s, done.
	Total 3 (delta 0), reused 0 (delta 0)
	To git@njames.github.com:njames/NextBigThing.git
	 * [new branch]      master -> master
	Branch master set up to track remote branch master from origin.
	10:10:44 (master) ~/squarecloud/NextBigThing$ 



Now if we refresh the GitHub repo page we can see all the commits made to it.

The rest of the world can now clone our repo and find out about the NextBigThing.

# Clone me baby, one more time

If we look at the repository properties we can see there is a url that we can use to clone the repo. There are several protocols we can use. Firstly we can use http or (and this is my preference) we can use ssh. I prefer ssh because once I have added my public ssh key to GitHub that is the way I am identified and it is seemless. 

The windows client uses http and you need to add your username and password. 

So staying with the command line, this is how we clone:

	git clone git@github.com:njames/NextBigThing.git 

# Summary

So in this blog, we have learned that git is a great distributed source control system.

We have learned how to:
1. init
2. add
3. commit
4. push
5. clone 

There is a lot more to get into with git but you can get started and then learn as you go. 

I hope you have found this a useful introduction and if this topic is of interest I will expand some of these topics.







































































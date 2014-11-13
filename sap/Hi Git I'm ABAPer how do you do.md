# Hi Git, I'm ABAPer how do you do?

When there was a call for community sessions before #SAPtd I jumped on the opportunity to present on two topics that I feel were going to be under-represented at the event.

1. Developer Communication Skills
2. Git

So I proposed two abstracts to the community talk selection committee and they told me that they while they were very excited about both topics they could only take one and they would take the first one. Well I was excited, but to be honest,  also a little dissapointed. As much as I wanted to talk on communication skills for developers I really wanted to introduce ABAPers to Git as a method of source code control as I know it will become very important as we move toward the HCP and OpenUI5.

As we got closer to the conference I was advised that one of other speakers that was selected had to withdraw and I was asked to prepare my second talk.

This presentation was only delivered at #SAPtd in Las Vegas so all the people going to Berlin will miss out. For this reason and that there should be a bit of an intro to Git here on SCN. I thought I would distill my off the cuff talk into a short blog for the benifit of the ABAPers in the universe.

# Welcome to Source Control

So source control is not a new subject to ABAPers. We are used to putting our code into transport requests, which then enables the code to be delivered across the landscape and into production in an orderly manner.

Let's for a moment think about what happens when you put a code artifact into a transport request. It's not that hard. You lock the object so that you and only you can work on the object at one time. Until you release your transport everyone else is prevented from doing anything to that object.

This is all well and good but what happens in the following scenario?

1. You are working on a new feature request.
2. A bug is discovered in production that related directly to your code object.

Well resolving the bug will obviously trump the new feature but you are halfway though your change and it will need to be parked while the emergency is dealt with.

The challenge is you change request might have a whole bunch of other object that are not ready to go to prod, let alone ready for regression testing.

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

You don't even need to have a remote system to use Git. You can install git on your Linux, Mac or Windows system and use it to version whatever files you like without ever sharing your code. Personally I have done this when I was working on a project but even though I wasn't having to work with other team members. This enabled me to version code and rollback changes if they didn't work.

For most scenarios though, you will need a remote system that all members of your team can access. For this GitHub is the answer to your needs. Is it the only answer? No, there are others but it is a great place to start.

So surf on over to GitHub and signup for an account. 

(insert image of GitHub initial screen)

Now that you have done that lets see what you have available to you:

You can explore the site in your own time but in the remainder of this introductory blog let me take you through the basis of the git workflow.

# First the init

Let's assume that we will start locally because you are on a long haul flight (with power) and have had a great new idea you want to code up

The first thing you are going to do is to initialise a folder to be tracked under source control.

As with most git commands you can either do this locally with the GUI apps, on the command line or on GitHub's website.

The command line is simply:

```
	git init

```


Even though windows does not really have a great command line, GitHub Windows ships with a commandline shell that runs under powershell. Cool huh.

The reason I like the command line so much is the even thought the native GUI application simplify everything so nicely sometimes the power that the commandline affords is the only way to get out of the muddle. So I like to build up the muscle memory in my fingers so that when it hits the fan and my colleague Windows commit has clobbered my commit I can recover without getting into a "tissie"

If you are creating a new repository on GitHub or using the windows (or mac) clients I think you will find it pretty easy. There are giant + buttons that make it really clear where to go to add something. 



















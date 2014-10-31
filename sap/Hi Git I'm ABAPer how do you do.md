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













# 7 More great reasons for Ubuntu

I wote a blog last month on just how much I have been enjoying Ubuntu as a desktop machine.

I can't see myself going back - I am a total convert. 

So just in the chance that I might win some more to the cause here are 7 more reasons why you might find Ubuntu to be your next OS choice

## 7. Wobby Windows 
Oh this is available for [other](https://www.google.com.au/search?q=wobbly+windows+mac) operating systems but having a few great window effects makes developement life much more fun.
Given I am running pretty standard Gnome Desktop, I use the [compviz](http://askubuntu.com/questions/449651/how-do-i-enable-wobbly-windows) plugin to get this working for me.
The Wobbly Windows adds a little stretchy and snappy effects to desktop windows but the best part is that compviz comes with other effects to snap windows into different parts of your desktop. So with a couple of keystrokes I can setup a browser window on one half of the screen and an editor (like sublime) on the right hand side of my screen

I can also quickly get several terminals up and snap them into the four quarters of the screen and use each one for a different server. Although you can achieve the same thing with ...

##  6. Terminator
These things can start to be a little 'my-terminal-is-better-than-your-terminal' but after I was introduced to [Terminator](http://gnometerminator.blogspot.com.au/p/introduction.html)
The best feature about Terminator is that you can have many windows and tabs open within the app to then replicate what I was doing with separate terminal sessions and snapping them to different corners of the screen.
To take this to another level (because that really doesn't light my fire that much) you can link windows together and issue the identical command to all windows. This was invaluable to me on a recent project where I was managing a cluster of servers and I wanted to issue the same query to each of them simulataiously.


## 5. Cowsay 
Again this is a pretty minor item, all things considered, but it does make logging messages that much more fun. 

I have been doing a lot of work with [Ansible](http://ansible.com/) an open source provisioning tool. I will have more to say on this in a future blog but for now lets if you are not familiar with it, then consider it a way to script your server deployments so that is easy to deploy new servers with identical configuration.

Ansible uses cowsay to output many of its messages to the screen as they the [playbooks](@todo get url) run. Given some playbooks take time it helps break up the monotony as the cows mooove across the screen.

Just to give you a feel of how cowsay can immediatley improve your life:

```
	18:36:20 nigeljames@DocBrown:~$ cowsay one point twentyone GigaWatts?!
	 _________________________________
	< one point twentyone GigaWatts?! >
	 ---------------------------------
	        \   ^__^
	         \  (oo)\_______
	            (__)\       )\/\
	                ||----w |	
	                ||     ||
	18:36:54 nigeljames@DocBrown:~$ 

```


## 4. Multiple virtual desktops 
I don't know how I will be able to work on 1080x768 again. I have grown used to multiple screens and not just multiple screens but multiple virtual screens. Ubuntu and Gnome make this a no brainer and you can easily have 4 virtual screens with real estate of 3840x2160. By splitting this into a virtual screen of 1920x1080 I can easily put different types of work on different virtual screens and focus on one particular type of work at once. I like to have a little PHP going on, with a little SAP UI5 here and perhaps email and other messaging on another. 
I can set up each screen with all the resources I need for that work and then leave it until I want to come back to it. This saves in context switch time as it is no trouble for my machine to leave an project or two open with the virtual machines that it needs and come back to it as I can.

I might restart my machine once a week if I need to, so to be able to set this up and then leave it all running is a great timesaver.

## 3. A Better understanding of your computer
In my [last blog](@todo get url) I mentioned that the commandline as one of the great benefits of Ubuntu. Now I love great user interfaces as much as the next person. In fact I am passionate about creating great user experience for my clients. One of the best ways to do this is to simplify, simplify, simplify and remove all the complexity that does not affect the transaction at hand.

As a developer and as a DevOperationalist you need to be familiar with what is going on with your servers. There are many great graphical programs that enable this but by using the command line I feel like I am operating at a much closer level to the computer and after a while of doing this the muscle memory kicks in and it becomes second nature.


## 2. Alias you, Alias me.
Whilst Jason Bourne is flying around the world with half a dozen passports an alias or two can be a great things to stick in your back pocket or or .bash_alias file.

An alias can take a long commannd line sequence and reduce it to a couple of easily typed letters. For example I have a scripted vagrant box that I used to have to get to the correct directory before starting it but with a simple and short script that I have aliased to two letters I can start that virtual machine and with another alias I can ssh into the machine and I am away. Actually not that I always need to ssh into the machine to do any work because I have mapped drives to the code base and can port forward port 80 on the guest to port 8000 on the host so all your development and testing can happen on your host machine but you will be secure in the knowledge that you have configured the virtual machine with the same software as the intended production server.


## 1. Configuarability
Yes I saved the best for last. The best part of Ubuntu or any other variant of linux is it's configuarability. If you don't like the UI or pretty much any part of the OS you can switch it out for another 
# ABAP - The Special Snowflake

The other day I poked the bear. Bears for the most part are things that should be left to their own devices as my Canadian friends will attest. 

The bear in this case was Dennis Howlett who has been a long time friend in the enterprisey space I met back as part of the media and influencers team at Sapphire and Teched events around 2006. 

Dennis was asking about the new ESME as part of a conversation about Diversity amoungst the SAP Mentors. (That is a blog for another day)

<blockquote class="twitter-tweet" data-conversation="none" data-lang="en"><p lang="en" dir="ltr">And where is the next <a href="https://twitter.com/hashtag/ESME?src=hash&amp;ref_src=twsrc%5Etfw">#ESME</a> team coming from?</p>&mdash; (((Den Howlett))) (@dahowlett) <a href="https://twitter.com/dahowlett/status/1009914069841862656?ref_src=twsrc%5Etfw">June 21, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

I replied: 

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr"><a href="https://twitter.com/hashtag/abapgit?src=hash&amp;ref_src=twsrc%5Etfw">#abapgit</a> is the biggest non sap led thing happening in SAP <br><br> Cc <a href="https://twitter.com/LarsHvam?ref_src=twsrc%5Etfw">@LarsHvam</a></p>&mdash; Nigel James (@njames) <a href="https://twitter.com/njames/status/1010670309941207040?ref_src=twsrc%5Etfw">June 23, 2018</a></blockquote>

 Now for background #ESME was a Enterprise Social Media Experiment that happened around 2006-7ish and could have been something cool. It became an apache project which was qudos to the people driving it [https://esme.apache.org/](https://esme.apache.org/).

So Den was asking about what the new cool edgy thing was around SAP these days. As I said in my tweet above it is my opinion that that is #AbapGit with a whole lot of whitespace until second.

Then (which is what I was hoping would happen ) Den looked into #AbapGit and dropped the following:

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Earlier today I took a look at <a href="https://twitter.com/hashtag/abapgit?src=hash&amp;ref_src=twsrc%5Etfw">#abapgit</a>. It is seriously good stuff. The tragedy is that VERY few <a href="https://twitter.com/SAPMentors?ref_src=twsrc%5Etfw">@SAPMentors</a> or others are committers in the context of the <a href="https://twitter.com/hashtag/SAP?src=hash&amp;ref_src=twsrc%5Etfw">#SAP</a> ecosystem. Shout out to <a href="https://twitter.com/grahamrobbo?ref_src=twsrc%5Etfw">@grahamrobbo</a> for waving the flag as vigorously as possible. cc <a href="https://twitter.com/njames?ref_src=twsrc%5Etfw">@njames</a> for poking me on this.</p>&mdash; (((Den Howlett))) (@dahowlett) <a href="https://twitter.com/dahowlett/status/1012206182499577857?ref_src=twsrc%5Etfw">June 28, 2018</a></blockquote>

The conversation that followed continued on for days across timezones picking up a whole lot of other voices and opinions on the way through. 

My attempt with this blog is to try and bring some of those opinions into one place and simulate the conversation further as to what sort of innovation we are looking for around the SAP technology space. And if you are short on time here is the tl;dr:

1. ABAP has legacy tools
2. ABAP has legacy culture
3. It is stuck there and will never ever move
4. ABAPGit is the best thing that happened to the ABAP ecosystem since ABAPUnit
5. Adoption of both of these toolsets are woefully low (Please see point 2.)
6. These are exactly the tools that we need to create CI/CD platforms for SAP landscapes.

There. If you want to skip to the next blog... go for it but first identify what culture is happening amoungst your ABAPers or your offshore team. 

If you want to enjoy the rest of the story then fasten your seatbelts, return your tray table to the upright position and hold on.

## #Disclaimer

Let me provide a disclaimer for those that love ABAP to a fault ( Hi [Michelle](https://people.sap.com/michelle.crapo5), Hi [Jellana](https://people.sap.com/jelena.perfiljeva2) ). Yes, ABAP is awesome and yes is does power half the planet if you believe SAP's marketing department but being great is not enough - all languages need to improve and get better. 

Am you saying that ABAP is not doing this? I mean that is a pretty provocative, click-baity title you put on this blog there Nigel.

Yes it is provocative and no - ABAP is innovating ( Hi [Horst](https://people.sap.com/horst.keller) ) There are incredibly talentent people inside and outside SAP pushing to improve the language, toolset and culture to become the best that is can be and when they are finished they will go some more.

The problem is that good ol' ABAP is for all intents closed source prorietory language. My other two favourite languages that include the letter P ( [Python](http://python.org) and [PHP](http://php.net/) ) are not. They have continually innovated around their core. Just the other day I saw [Zeev Suraski](https://twitter.com/zeevs) one of the co-architects of PHP saying that the [next release of PHP](https://twitter.com/andigutmans/status/1013291330917711872) would be [4-5 times faster](https://www.phpclasses.org/blog/post/493-php-performance-evolution.html#improvements) than version 7. This is not bad given that version 7 was twice as fast as version 5.x that preceeded it.

What languages carry with them - more than anything else is legacy baggage. PHP certainly does - and routinely get bagged for it but many companies including Facebook, Slack, and Mailchimp have PHP at the heart of their business and serve many millions of customers. Enterprisey enought for you? ABAP, coming from its FORTRAN and COBOL roots has a very verbose nature and weird keywords. That's why we "love" it right? [Many](https://help.sap.com/doc/abapdocu_750_index_htm/7.50/en-US/index.htm?file=abennews-750.htm) [improvements](https://help.sap.com/http.svc/rc/abapdocu_752_index_htm/7.52/en-US/index.htm) over the years have been welcome and the code we write in ABAP today is not the code we wrote 20 years ago.

What they also bring is toolsets, "tecosystems" ( Thanks [@sogrady](https://twitter.com/sogrady) ) and a culture that grows up around them. 

## #ABAPGit can shift the ABAP CI landscape

My thesis in this twitter thread that developed was that #ABAPGit could bring new ways of deploying code to the ABAP Ecosystem just as #UI5 has brought innovation to the Front End and HANA has brought innovation to the database.

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Mindsets like &#39;caching&#39; tables to hold monthly summarys that are no longer needed in S4/HANA. If they can innovate around the DB and drop tables why not around CI/CD and ditch STMS? <a href="https://twitter.com/BoobBoo?ref_src=twsrc%5Etfw">@BoobBoo</a> - your turn to pitch in :)</p>&mdash; Nigel James (@njames) <a href="https://twitter.com/njames/status/1012480323114811392?ref_src=twsrc%5Etfw">June 28, 2018</a></blockquote>

Other believe the culture needs to come first:

<blockquote class="twitter-tweet" data-conversation="none" data-lang="en"><p lang="en" dir="ltr">Just quickly chime in here and posit that tooling is not the biggest reason <a href="https://twitter.com/hashtag/sap?src=hash&amp;ref_src=twsrc%5Etfw">#sap</a> customers don’t deploy multiple times a day. Tooling certainly helps - but the “enterprise” mindset that has formed over 30+ years is really hard to break down</p>&mdash; Graham Robinson (@grahamrobbo) <a href="https://twitter.com/grahamrobbo/status/1012468293079203840?ref_src=twsrc%5Etfw">June 28, 2018</a></blockquote>

Graham is right though. Enterprise mindset is hard to break down.

In other development enviroments the deploy to prod as often as required is commonplace. When I gave a talk about [learning #git](http://njames.github.io/talks/SAPTechEd2015/GetIntoGit/DEV110.html#1) back at #SAPTeched in 2015 I had a guy from Github in the audience. Thankfully he identifed himself after the talk and told me how they deploy regularly with the record from issue being opened to fix in production being "2 minutes"* (Actual time may vary -  but rest assured it was not 6 months) 

I have since heard similar stories at Amazon, Facebook, Netflix. Why does the enterprise (read ABAP based platforms ) have to be different?

## The toolsets are available

Chris Paine nailed it early on:
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">The combo of abap unit test, a branch based repo and then bringing in tools to manage automatic migration and testing could have the possibility to pull ABAP based development into the 21st century. But why hammer the round peg into square hole?</p>&mdash; Chris Paine (@wombling) <a href="https://twitter.com/wombling/status/1012254340751347712?ref_src=twsrc%5Etfw">June 28, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>


And there you have it: 
	* Unit Test
	* Decentralised Branch Based Repository
	* Automatic Migration
	* Branch based deployment

People like [@grmpyprogrammer](https://twitter.com/grmpyprogrammer), Chris Hartjes, have been preaching Unit Testing to the PHP Community for years, probably 18 years. The toolsets and workflow are well established and while it has taken people like Chris years and years of banging the drum the message has gotten through. 

ABAP Unit has been with us for at least a decade but how many of us unit test our ABAP code? How many of the 'offshore'	code factories include ABAP Unit tests as part of their deliverable?

Where is the ABAP Unit culture? Happily there are [more voices](https://blogs.sap.com/2018/03/18/sap-open-abap-unit-testing-course-week-one/) promoting unit testing recently.

Even in the Java world JUnit and friends have made testing common. Which is why Chris Paine is happy developing extensions in the cloudy world:

<blockquote class="twitter-tweet" data-conversation="none" data-lang="en"><p lang="en" dir="ltr">Rather than rebuilding the wheel to fit the juggernaut, keep the juggernaut running as standard as possible and apply enhancements outside of it. This is <a href="https://twitter.com/hashtag/SaaS?src=hash&amp;ref_src=twsrc%5Etfw">#SaaS</a> enhanced with <a href="https://twitter.com/hashtag/PaaS?src=hash&amp;ref_src=twsrc%5Etfw">#PaaS</a></p>&mdash; Chris Paine (@wombling) <a href="https://twitter.com/wombling/status/1012467270377824256?ref_src=twsrc%5Etfw">June 28, 2018</a></blockquote>

But to do this he is using unit testing, branched based source control and automatic deployment mechanism. ( Chris may want to chime in and correct me here I dont actually know his workflow I am assuming it based on his tweets. )

Ethan Jewett had some really great comments to add - he joined in with: 

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">No, really not. It’s a PITA, but every other platform in the world handles platform version changes and branches at the same time. Once you have code decoupled from the runtime, then developing and testing on a new patch level is easy peasy.</p>&mdash; Ethan Jewett (@esjewett) <a href="https://twitter.com/esjewett/status/1013584122072190976?ref_src=twsrc%5Etfw">July 2, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>


And unsurprisingly (as Ethan always has great things to say) there is another thread on modern ABAP practices starting here (from 2016) :

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Great article by <a href="https://twitter.com/esjewett?ref_src=twsrc%5Etfw">@esjewett</a> <br>Implementing modern practices in an ABAP development shop <a href="https://t.co/1pAkgvc9vb">https://t.co/1pAkgvc9vb</a><br>cc <a href="https://twitter.com/ABAPCodeRetreat?ref_src=twsrc%5Etfw">@ABAPCodeRetreat</a> <a href="https://twitter.com/majcon?ref_src=twsrc%5Etfw">@majcon</a></p>&mdash; Christian Drumm 🇪🇺 (@ceedee666) <a href="https://twitter.com/ceedee666/status/814758110724259840?ref_src=twsrc%5Etfw">December 30, 2016</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

and again as Matt Harding pointed out that this conversation has been going on for quite some time pointing back to a tweet from [Chris Kernaghan](https://twitter.com/BoobBoo) from 2014.

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">.<a href="https://twitter.com/njames?ref_src=twsrc%5Etfw">@njames</a> Being going on for longer than a few days! <a href="https://t.co/7YrlRRLV24">https://t.co/7YrlRRLV24</a></p>&mdash; Matt Harding (@mattharding) <a href="https://twitter.com/mattharding/status/1013663919875878913?ref_src=twsrc%5Etfw">July 2, 2018</a></blockquote>

And the kicker which really sums up the ABAP Culture is this:

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">I have to agree with <a href="https://twitter.com/BoobBoo?ref_src=twsrc%5Etfw">@BoobBoo</a>. The level to which many ABAPers are convinced that what they are doing is a special snowflake is astounding. Way beyond what I see on other platforms. I think SAP has to take some of the credit for that culture.</p>&mdash; Ethan Jewett (@esjewett) <a href="https://twitter.com/esjewett/status/1012664691779428352?ref_src=twsrc%5Etfw">June 29, 2018</a></blockquote>


Personally - I have never wanted to stay with my own set of tools. I am not an ABAPer. I solve problems that can (sometimes) be solved with a computer program and I am happy to say that over the years I have contributed to many sucessful implementations just as I have contributed to things that have never seen the light of production.

About four years ago I took on a client who was the farthest from SAP as anyone could imagine. They were a content platform startup. Small team using PHP and a little framework called [Laravel](https://laravel.com/). Thankfully they didn't let me at the code. I did a more robust data replication proof of concept for them. While I was there I learned a lot about how this team used:

	1. Unit Testing
	2. Decentralised Branch Based Repository
	3. Automatic Migration
	4. Branch based deployment

Sound familiar? Every other team and platform does this. Ethan is right. ABAP is a Special Snowflake.

So here is the cultural challenge to all those who are die hard ABAPers. You need to embrace the new tools and new ways of doing things. 

I hope this has raised a thought and sparked more conversation. 

Let's not be doing something because it is Not Invented Here.

I will leave you with the [Knights who say NIH](https://www.youtube.com/watch?v=zIV4poUZAQo)


[and yes I wrote this blog in [markdown](http://commonmark.org/) using [Sublime Text 3](https://sublimetext.com/3) and used github to [version control it](https://github.com/njames/blogs/blob/master/sap/SCN%20-%20ABAP%20-%20The%20Special%20Snowflake.md) ]
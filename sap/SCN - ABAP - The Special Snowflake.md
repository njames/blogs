# ABAP - The Special Snowflake

The other day I poked the bear. Bears for the most part are things that should be left to their own devices as my Canadian friends will attest. 

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr"><a href="https://twitter.com/hashtag/abapgit?src=hash&amp;ref_src=twsrc%5Etfw">#abapgit</a> is the biggest non sap led thing happening in SAP <br><br> Cc <a href="https://twitter.com/LarsHvam?ref_src=twsrc%5Etfw">@LarsHvam</a></p>&mdash; Nigel James (@njames) <a href="https://twitter.com/njames/status/1010670309941207040?ref_src=twsrc%5Etfw">June 23, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

#ESME was a Enterprise Social Media Experiment that happened around 2007ish and could have been something cool. It became an apache project which was qudos to the people driving it https://esme.apache.org/.

With that backgroud Den was asking about what the new cool edgy thing was around SAP these days. As I said in my tweet above it is my opinion that that is #AbapGit with a whole lot of whitespace until second.

Then (which is what I was hoping would happen ) Den looked into #AbapGit and dropped the following:

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Earlier today I took a look at <a href="https://twitter.com/hashtag/abapgit?src=hash&amp;ref_src=twsrc%5Etfw">#abapgit</a>. It is seriously good stuff. The tragedy is that VERY few <a href="https://twitter.com/SAPMentors?ref_src=twsrc%5Etfw">@SAPMentors</a> or others are committers in the context of the <a href="https://twitter.com/hashtag/SAP?src=hash&amp;ref_src=twsrc%5Etfw">#SAP</a> ecosystem. Shout out to <a href="https://twitter.com/grahamrobbo?ref_src=twsrc%5Etfw">@grahamrobbo</a> for waving the flag as vigorously as possible. cc <a href="https://twitter.com/njames?ref_src=twsrc%5Etfw">@njames</a> for poking me on this.</p>&mdash; (((Den Howlett))) (@dahowlett) <a href="https://twitter.com/dahowlett/status/1012206182499577857?ref_src=twsrc%5Etfw">June 28, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

The conversation that followed continued on for days across timezones picking up a whole lot of other voices and opinions on the way through. 

My attempt with this blog is to try and bring some of those opinions into one place and simulate the conversation further as to what sort of innovation we are looking for around the SAP technology space. 

Let me provide a disclaimer for those that love ABAP to a fault ( Hi Michelle, Hi Jellana ) . Yes, ABAP is awesome and yes is does power half the planet if you believe SAP's marketing department but being great is not enough - all languages need to improve and get better. 

Am you saying that ABAP is not doing this? I mean that is a pretty provocative, click-baity title you put on this blog there Nigel.

Yes is is provocative and no - ABAP is innovating ( Hi Horst ) There are incredibly talentent people inside and outside SAP pushing to improve the language, toolset and culture to become the best that is can be and when they are finished they will go some more.

The problem is that good ol' ABAP is for all intents closed source prorietory language. My other two favourite languages that include the letter P ( Python and PHP ) are not. They have continually innovated around their core. Just the other day I saw [Zeev Suraski](https://twitter.com/zeevs) one of the co-architects of PHP saying that the [next release of PHP](https://twitter.com/andigutmans/status/1013291330917711872) would be [4-5 times faster](https://www.phpclasses.org/blog/post/493-php-performance-evolution.html#improvements) than version 7. This is not bad given that version 7 was twice as fast as version 5.x that preceeded it.

What languages carry with them - more than anything else is legacy baggage. ABAP coming from its FORTRAN and COBOL roots has a very verbose nature and weird keywords. That's why we "love" it right? 

What they also bring is toolsets, "tecosystems" ( Thanks [@sogrady](https://twitter.com/sogrady) ) and a culture that grows up around them. 

My thesis in this twitter thread that developed was that #ABAPGit could bring new ways of deploying code to the ABAP Ecosystem just as #UI5 has brought innovation to the Front End and HANA has brought innovation to the database.

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Mindsets like &#39;caching&#39; tables to hold monthly summarys that are no longer needed in S4/HANA. If they can innovate around the DB and drop tables why not around CI/CD and ditch STMS? <a href="https://twitter.com/BoobBoo?ref_src=twsrc%5Etfw">@BoobBoo</a> - your turn to pitch in :)</p>&mdash; Nigel James (@njames) <a href="https://twitter.com/njames/status/1012480323114811392?ref_src=twsrc%5Etfw">June 28, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

Graham is right though. Enterprise mindset is hard to break down.

In other development enviroments the deploy to prod as often as required is commonplace. When I gave a talk about [learning #git](http://njames.github.io/talks/SAPTechEd2015/GetIntoGit/DEV110.html#1) back at #SAPTeched in 2015 I had a guy from Github in the audience. Thankfully he identifed himself after the talk and told me how they deploy regularly with the record from issue being opened to fix in production being "2 minutes"* (Actual time may vary -  but rest assured it was not 6 months) 

I have since heard similar stories at Amazon, Facebook, Netflix. Why does the enterprise have to be different?

Chris Paine nailed it early on:
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">The combo of abap unit test, a branch based repo and then bringing in tools to manage automatic migration and testing could have the possibility to pull ABAP based development into the 21st century. But why hammer the round peg into square hole?</p>&mdash; Chris Paine (@wombling) <a href="https://twitter.com/wombling/status/1012254340751347712?ref_src=twsrc%5Etfw">June 28, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>


And there you have it: 
	* Unit Test
	* Decentralised Branch Based Repository
	* Automatic Migration
	* Branch based deployment

People like [@grmpyprogrammer](https://twitter.com/grmpyprogrammer) have been preaching Unit Testing to the PHP Community for years. Probably 18 years. The toolsets and workflow are well established and while it has taken people like Chris years and years of banging the drum the message has gotten through. 

Even in the Java world JUnit and friends have made testing common.

ABAP Unit has been with us for at least a decade but how many of us unit test our ABAP code? How many of the 'offshore'	code factories include ABAP Unit tests as part of their deliverable?

Where is the ABAP Unit culture? Happily there are [more voices](https://blogs.sap.com/2018/03/18/sap-open-abap-unit-testing-course-week-one/) promoting unit testing recently.

Ethan Jewett had some really great comments to add - he joined in with: 

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">No, really not. It’s a PITA, but every other platform in the world handles platform version changes and branches at the same time. Once you have code decoupled from the runtime, then developing and testing on a new patch level is easy peasy.</p>&mdash; Ethan Jewett (@esjewett) <a href="https://twitter.com/esjewett/status/1013584122072190976?ref_src=twsrc%5Etfw">July 2, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>


And unsurprisingly (as Ethan always has great things to say) there is another thread on modern ABAP practices starting here (from 2016) :

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Great article by <a href="https://twitter.com/esjewett?ref_src=twsrc%5Etfw">@esjewett</a> <br>Implementing modern practices in an ABAP development shop <a href="https://t.co/1pAkgvc9vb">https://t.co/1pAkgvc9vb</a><br>cc <a href="https://twitter.com/ABAPCodeRetreat?ref_src=twsrc%5Etfw">@ABAPCodeRetreat</a> <a href="https://twitter.com/majcon?ref_src=twsrc%5Etfw">@majcon</a></p>&mdash; Christian Drumm 🇪🇺 (@ceedee666) <a href="https://twitter.com/ceedee666/status/814758110724259840?ref_src=twsrc%5Etfw">December 30, 2016</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

and again as Matt Harding pointed out that this conversation has been going on for quite some time pointing back to a tweet from [Chris Kernaghan](https://twitter.com/BoobBoo) from 2014.

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">.<a href="https://twitter.com/njames?ref_src=twsrc%5Etfw">@njames</a> Being going on for longer than a few days! <a href="https://t.co/7YrlRRLV24">https://t.co/7YrlRRLV24</a></p>&mdash; Matt Harding (@mattharding) <a href="https://twitter.com/mattharding/status/1013663919875878913?ref_src=twsrc%5Etfw">July 2, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>











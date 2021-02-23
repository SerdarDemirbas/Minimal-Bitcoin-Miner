Minimal-Bitcoin-Miner
=====================

A very simple CPU based Bitcoin Miner in C#. Uses the GETWORK protocol to connect to pool. A great reference implementation if you are trying to understand how Bitcoin mining works.

<b>Edit 2017: Not actually fit for mining - the GETWORK protocol isn't supported anymore by most pools</b>

------------------------

NOTLAR
=====================

Bitcoin Forum
Other => Beginners & Help => Topic started by: lithander on May 11, 2013, 03:06:18 PM

Title: My lightweight C# Bitcoin Miner
Post by: lithander on May 11, 2013, 03:06:18 PM
I've written a very simple CPU based Bitcoin Miner in C#. Only about 300 lines of code but functional.

It uses the basic GETWORK protocol to connect to pools and mines at 400Kh/s a second. Not enough for serious mining but enough to find a valid share eventually, submit it to the pool server and be happy about the fact that you understand every single line of code that made it happen!

If you are trying to understand how Bitcoin mining works and are frustrated about not finding a reference implementation that is minimal and easy to understand (like me, 2 days ago) here's my contribution:

https://github.com/lithander/Minimal-Bitcoin-Miner

Title: Re: My lightweight C# Bitcoin Miner
Post by: TrollByFire on May 11, 2013, 04:09:00 PM
Thank you for this.  I'm currently doing some development work, and this minimal implementation will go a long way.

Title: Re: My lightweight C# Bitcoin Miner
Post by: shodan86 on May 11, 2013, 04:09:37 PM
looks like an interesting way to learn a bit more about the technical site of bitcoins, thanks a lot will have a look.

Title: Re: My lightweight C# Bitcoin Miner
Post by: betonbro on May 11, 2013, 08:12:13 PM
Hi, nice :)

Is it possible to use it to mine Litecoin or Feathercoin?

Have tried it with mining-foreman.org pool but it says:
ERROR Didn't find valid 'data' in Server Response


Title: Re: My lightweight C# Bitcoin Miner
Post by: lithander on May 11, 2013, 10:48:26 PM
glad you like it! :)

@betonbro: I implemented the pool communication based on the information on: https://en.bitcoin.it/wiki/Getwork and tested it with btcguild and bitcoin.cz pools.

I'm not familiar with Litecoin and Feathercoin so no idea what it would take to mod it to support that.

Title: Re: My lightweight C# Bitcoin Miner
Post by: judasiscariot on May 12, 2013, 12:29:15 AM
This is awesome!  Thank you.  I'd also be interested in how to go about an scrypt implementation. 

Title: Re: My lightweight C# Bitcoin Miner
Post by: lithander on May 12, 2013, 12:38:32 AM
I haven't looked into litecoin mining, yet. So I can't help you with scrypt! :)

I just started to learn all that stuff a couple of days ago. In fact when I wanted to write a blogpost about my miner I realized how awkwardly unfamiliar a lot of terms and principles still are. If you could have a quick look and correct potential misconception before I make a fool about myself that would be awesome. Blogpost is here: http://blog.pixelpracht.net/

Title: Re: My lightweight C# Bitcoin Miner
Post by: OB1 on May 12, 2013, 07:34:18 AM
Quote
Nonetheless incredible amounts of electricity (~1 GW/h) are wasted on mining Bitcoins which is basically spend calculating zillion’s of SHA256 hashes.
::)
Failed.
Source also failed (Virtual Bitcoin Mining Is a Real-World Environmental Disaster)
With that, how much of a failure is this lightweight C# Bitcoin Miner?

Title: Re: My lightweight C# Bitcoin Miner
Post by: flatfly on May 12, 2013, 07:49:26 AM
Really nice and easy to understand! Thanks for this.

Title: Re: My lightweight C# Bitcoin Miner
Post by: lithander on May 12, 2013, 09:29:22 AM
Quote from: OB1 on May 12, 2013, 07:34:18 AM
Quote
Nonetheless incredible amounts of electricity (~1 GW/h) are wasted on mining Bitcoins which is basically spend calculating zillion’s of SHA256 hashes.
::)
Failed.
Source also failed (Virtual Bitcoin Mining Is a Real-World Environmental Disaster)
With that, how much of a failure is this lightweight C# Bitcoin Miner?

Failed in what way? It doesn't reflect your opinion or factual errors?

Title: Re: My lightweight C# Bitcoin Miner
Post by: flatfly on May 12, 2013, 02:18:59 PM
About the binary that is included in your repo: could you post instructions on how to build it?
Can it be built using a free compiler? I have zero C# experience...

That way, anyone can verify that it is indeed derived from the source code. I'm sure it is, and am running it in a VM as a safety measure anyway, but this community is paranoid about new binaries in general, as I'm sure you'll understand.

Title: Re: My lightweight C# Bitcoin Miner
Post by: SunCoin on May 12, 2013, 02:24:33 PM
Hey,
that was a great work ... Now i can see how it works in a simple way ...
Thanks a lot

Title: Re: My lightweight C# Bitcoin Miner
Post by: ppcko on May 12, 2013, 03:02:13 PM
Nice. Thanks for sharing.

Title: Re: My lightweight C# Bitcoin Miner
Post by: FaradayC on May 12, 2013, 04:11:12 PM
Wow... That's amazing... I'll check out your code :)

Title: Re: My lightweight C# Bitcoin Miner
Post by: aes1 on May 12, 2013, 07:23:06 PM
Neat. I had no idea mining could be that simple.

I compiled the source on an OS X machine by downloading Mono SDK from http://www.go-mono.com/mono-downloads/download.html (http://www.go-mono.com/mono-downloads/download.html). The compilation step and running the compiled binary was as easy as:

Quote
$ mcs Program.cs
$ mono Program.exe

Let's see if I actually manage to get any bitcoins with my 180 Kh/s miner :)

Next step: actually understanding what it does

Title: Re: My lightweight C# Bitcoin Miner
Post by: JS2007 on May 12, 2013, 07:34:55 PM
Good job, will look into this when I got some spare time... Easy sample code is always helpful for understanding concepts :)

Title: Re: My lightweight C# Bitcoin Miner
Post by: flatfly on May 12, 2013, 07:46:01 PM
Quote from: aes1 on May 12, 2013, 07:23:06 PM
Neat. I had no idea mining could be that simple.

I compiled the source on an OS X machine by downloading Mono SDK from http://www.go-mono.com/mono-downloads/download.html (http://www.go-mono.com/mono-downloads/download.html). The compilation step and running the compiled binary was as easy as:

Quote
$ mcs Program.cs
$ mono Program.exe

Let's see if I actually manage to get any bitcoins with my 180 Kh/s miner :)

Next step: actually understanding what it does


Hmmm sorry to dampen your enthusiasm, but consider yourself lucky if you get one cent per week...

see:
http://tpbitcalc.appspot.com/?difficulty=11187257.4614&hashrate=0.2&exchangerate=114.40&bitcoinsperblock=25.00&rigcost=99.00&powerconsumption=40.00&powercost=0.10&investmentperiod=355

Title: Re: My lightweight C# Bitcoin Miner
Post by: aes1 on May 13, 2013, 02:33:22 PM
Quote from: flatfly on May 12, 2013, 07:46:01 PM
Hmmm sorry to dampen your enthusiasm, but consider yourself lucky if you get one cent per week...

see:
http://tpbitcalc.appspot.com/?difficulty=11187257.4614&hashrate=0.2&exchangerate=114.40&bitcoinsperblock=25.00&rigcost=99.00&powerconsumption=40.00&powercost=0.10&investmentperiod=355

Yeah,

after a day or so of mining, I finally got one share in btcguild... worth 0.00000071 BTC. Hurray!

Funny to think that it's more profitable to spend your time at bitcoin faucets. Or to collect recyclable bottles and return them to the store. Well, it was a nice exercise.

Title: Re: My lightweight C# Bitcoin Miner
Post by: Constantinex13 on May 13, 2013, 02:38:10 PM
Awesome, This is much more effective than running lets say bfgminer, on a mid-range laptop (might as well mine while I'm at work!) lol

Title: Re: My lightweight C# Bitcoin Miner
Post by: yager on May 13, 2013, 03:39:57 PM
Quote from: Constantinex13 on May 13, 2013, 02:38:10 PM
Awesome, This is much more effective than running lets say bfgminer, on a mid-range laptop (might as well mine while I'm at work!) lol

Good Idea, I might get my work pcs "working" for a change lol.

Title: Re: My lightweight C# Bitcoin Miner
Post by: esbex on May 13, 2013, 04:59:49 PM
Thanks for this, good to have some basic code to work off of and learn...

Title: Re: My lightweight C# Bitcoin Miner
Post by: catalyzm on May 15, 2013, 11:43:55 PM
Nice to see people working on BTC with C#


Powered by SMF 1.1.19 | SMF © 2006-2009, Simple Machines

Tacocoin Testnet
================

Informations, usage and code snippets of tacocoin -testnet mode for developers, who needs a stable playground for their applications.

**Note: If you develop some software around the tacocoin, you should better use the implemented testnet to prevent loosing your real tacocoins.**

##### Table of Contents
* [What is the testnet?](#description)  
* [What do you need to use the testnet?](#usage)  
* [Ports, ports, ports](#ports) 
* [Getting some testtaco](#getting)   
  * [via mining](#mining)  
* [Well done!](#done)


<a name="description"/>
## What is the testnet?

The `tacocoin testnet` is an alternative tacocoin network with a separate blockchain. Since it uses a different blockchain, the testnet doesn't operate with the real tacocoin, but rather with what we call _testtaco_. These testtaco have `no monetary worth`. This allows developers to test their tacocoin applications on the testnet `without risking to lose the real tacocoin` or having to pay transactions fees.

<a name="usage"/>
## What do you need to use the testnet?

Well, this ist totally simple, if you have installed the `tacocoin wallet (tacocoin-qt/tacocoind)`. You can just add an arguement to the command via commandline. Like this:

```bash
tacocoin-qt -testnet 
or
tacocoind -testnet
```

Or you can set the specific settings through a setting file, called `tacocoin.conf`.

**tacocoin.conf setting file**
> You find the config file in your home directory.
> ```
> linux   -> ~/.tacocoin/tacocoin.conf
> windows -> ~/AppData/Roaming/tacoCoin/tacocoin.conf
> ```

For this guide we use the tacocoin.conf file for our settings. This is definitly the best way, instead of continously typing the hole commandline arguments into the console.

If this config file doesn't exists, we going to create it. And if it exists, just alter it.

Just add the following lines to the tacocoin.conf:
```bash
daemon = 1
server = 1
testnet = 1
rpcport = 44555
addnode = 107.170.152.173
# we can totally add more nodes.
# if one node goes down. the testnet could be run with other nodes.
# just think about it, as a kind of failsafe node.
```

> If you like your node to be added here. Let me know.

<a name="ports"/>
## Ports, ports, ports

Let's talk about the ports! As you realized yourself, the testnet mode uses different ports. Here's an overview:

Ports/Description | tacocoin-qt/tacocoind |tacocoin Testnet      |
------|-----------------------|----------------------|
rpc   | 21042                 | 5745                |
p2p   | 11042                 | 5744                |


<a name="getting"/>
## Get some testtaco

So everything is now set up. And you should `get some testtaco`!

<a name="mining"/>
### via mining

> If you interested in running a mining pool. And would like to test your pool via the testnet mode. Please note that because this is testnet, the hash rate is extremely low. Please do not use GPU miners on this, you'll go straight past 51% attack and somewhere in a 99% attack. **CPU miners strongly recommended. And should be used only!**

You can try to mine it yourself with the implemented cpu miner in the tacocoin-qt/tacocoind.

**linux console style**
```bash
# now we tell tacocoind to enable the mining procedure and to use 1 core of the cpu.
./tacocoind setgenerate true 1
```

After a short time, you should disable it. Believe me, it is sufficient. For an hour mining i got about >500K testtaco.

```bash
# disable the mining procedure
./tacocoind setgenerate false
```

**windows style**

Just open the mining tab in the tacocoin-qt an set up the cpu miner.

**linux/windows style**

If you like to be system independent, you can also set this via the tacocoin.conf setting file.
Add to the tacocoin.conf:
```bash
# this enables the mining procedure
gen = 1
```

<a name="faucets"/>
### via faucets

None Yet

> If you like your testtaco-faucet to be added here. Let me know.

<a name="done"/>
## Well done.

*That's it!*
You have successfully set up your own client for the tacocoin testnet. This is a perfect part of your new development environment. You don't need to be scared of losing real taco during your test runs. Great work, everybody!

**If you still have any questions, feel free to visit the [`/r/tacocoindev`](http://www.reddit.com/r/tacocoindev) subreddit. Every questions about development and the testnet is an added value for the community.**




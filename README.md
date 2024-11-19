# SRTLA OpenWRT source packages

This is a package source feed for the OpenWRT build system adding the SRTLA packages

## Why?

The SRTLA tools are a fork of the SRT (Secure Reliable Transport) libraries/tools that are commonly used for live and low latency video transport over unreliable network links. SRTLA adds functionality to do link aggregation natively over multiple connections. An ideal use case for this would be over multiple 4G/5G connections for added redundancy or bandwidth.

OpenWRT is an open source router software that can be run on many platforms. As this implies, it is tailor made to handle various routing and network connectivity duties compared to trying to make a run-of-the-mill desktop OS handle it.

The `srtla_send` tool that sends an SRT feed over multiple links requires its own direct access to said network links. This means that while running OpenWRT to manage these, `srtla_send` needs to run on OpenWRT itself to see the individual network links. It can then be fed by a LAN connected device via a normal SRT feed.

## Next steps

In addition to the ever growing TODO list below, after exploring the Belabox platform as a whole, I'd like to explore porting this over to OpenWRT to make the networking side more accessible and expandable. No ETA. Will be worked on as my free time allows.

## Disclaimer

For the time being this repo is a WIP. At any time it may or may not be working as intended. I will keep an active status below up to date as new commits are added.

**Current Status:** ✅ Compiles and runs. Tested on an RPi5. Barebones functionality of the original `srtla_send` tool is there.

## TODO:

* Confirm base functionality on an OpenWRT install
* Add firewall hotplug script to reload IP list when an interface is added/goes up/down
* Add proper init scripts and defaults to make it more user friendly
* Integrate some config options into the OWRT uci/config system
* Add some logging to OWRT's existing log system, prioritizing network based messages
* Rework repo to pull the core source from the upstream Belabox repo as OpenWRT's build system allows

[![Slack Status](http://slack.counterparty.io/badge.svg)](http://slack.counterparty.io)

counterblock
==============

`counterparty-classic-counterblock` provides additional services to Counterwallet beyond those offered in the API provided by `counterparty-server`. It features a full-fledged JSON RPC-based API, which services Counterwallet as well as any 3rd party services which wish to use it. `counterparty-classic-counterblock` has an extensible architecture, and developers may write custom plugins for it, which are loaded dynamically and allow them to extend `counterparty-classic-counterblock` with new parsing functionality, write gateways to other currencies or services, and much more.

With its set of core-plugins, `counterparty-classic-counterblock` provides a more high-level data processing, and an API that layers on top of `counterparty-server`’s API. `counterblock` generates and allows querying of data such as market and price information, trade operations, asset history, and more. It is used extensively by Counterwallet itself, and is appropriate for use by applications that require additional API-based functionality beyond the scope of what `counterparty-server` itself provides.

# Installation

For a simple Docker-based install of the Counterparty Classic software stack, see [this guide](https://github.com/jdogresorg/counterparty-classic-feddnode/docs/).

# Documentation

[Counterblock API](./docs/api.md)
[Writing counterblock Plug-in Modules](./docs/modules.md)

# Manual installation

(Linux only.) First, install `mongodb` and `redis`, and have an instance of `bitcoind` (`addrindex` branch) and [`counterparty-server`](https://github.com/jdogresorg/counterparty-classic-lib) running.

Then, download and install `counterparty-classic-counterblock`:

```
$ git clone https://github.com/jdogresorg/counterparty-classic-counterblock.git
$ cd counterblock
$ sudo pip3 install -r requirements.txt
$ sudo python3 setup.py install
```

Then, launch the daemon via the following command, with the passwords set as appropriate:

```
$ counterblock --backend-password=rpc --counterparty-password=rpc server
```

Further command line options are available via:

* `$ counterblock --help`

# License notices

This product will download/use GeoLite2 data created by MaxMind, available from
<a href="https://dev.maxmind.com/geoip/geoip2/geolite2/">https://dev.maxmind.com/geoip/geoip2/geolite2/</a>. Under **Creative Commons Corporation Attribution-ShareAlike 4.0 International License** (the “Creative Commons License”)

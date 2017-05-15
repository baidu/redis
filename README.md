<img src="https://raw.githubusercontent.com/ksarch-saas/cc/master/doc/pic/redis.png" height="80"></img>
[![Gitter](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/ksarch-saas/RedisCluster?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

### Intro

This is a Redis Cluster Controller to control the state of the cluster nodes and provide http api and tools(both command line and web ui).

It is production-ready and used at [baidu.com](http://www.baidu.com), with a scale of 2000+ machines.

The system should be used conbining with `https://github.com/ksarch-saas/redis`, `https://github.com/ksarch-saas/r3proxy` and `https://github.com/ksarch-saas/cc`

### Features

* Multi-IDC Support, every node has a tag, never elect node in a backup region as master.
* Replication via siblings, do partial resync from new master if it is our sibling.
* Builtin web console and command line tools for realtime monitor and control.
* Configurable read preferences, you can read from primary, primary_preferred or neareat region.
* Global failover constraint, if many many clusters deploy on the same machine pool, two clusters will never exec failover jobs at the same time.
* Slot rebalance.
* Cluster configuration convergence, topology of cluster maintained by redis cluster nodes

### Tutorial

[简体中文](doc/tutorial_zh.md)

### Architecture

<img src="https://raw.githubusercontent.com/ksarch-saas/cc/master/doc/pic/rediscluster1.png" height="480"></img><br/>
<img src="https://raw.githubusercontent.com/ksarch-saas/cc/master/doc/pic/rediscluster2.png" height="800"></img>


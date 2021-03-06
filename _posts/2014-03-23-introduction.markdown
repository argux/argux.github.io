---
layout: docs
title:  "Introduction to Argux"
categories: news docs
---

Argus has a different design then traditional monitoring applications. 
It's main design aspects are described below.

## Decentralised configuration ##
The configuration that determines what is monitored on a client, with
what frequency, and if that information will be leaked to a remote
server is managed locally. The central server can not influence the
frequency at which information is receive, or choose to retrieve
information that is not authorised by the client.

The client publishes a list of authorised items to the server. The
server subscribes to the items he is interested in. The client
requests the list of subscribed items and starts sending the
information.

Since the client is the initiator in all of this, this brings a
number of advantages over the traditional 'polling' architecture
other systems use.

1. The administrator of the client system can tune the monitoring
behaviour to the requirements and capabilities of that system -
there is no way a central monitoring system could suddenly hammer
your client.
2. The client can 'queue' the data for a limited time in case the
server is temporarily unavailable, therefore limiting the chance of
missing data.
3. The administrator of the client determines which information is
*'leaked'* to the external system, introducing the possibility of
providing 'hosted' argux-services.

Ofcourse, you could argue that decentralising the configuration of
your monitoring solution is a step backwards in time. But there are
other systems that can be used to centrally manage your systems,
including argux, like puppet or chef.

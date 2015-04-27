## Overview

This repo contains the definitions for **all** IMOS data collections, including:

* harvesters (processes which ingest from source format to our storage)
* publishing (i.e. geoserver layers)
* metadata (i.e. geonetwork records)
* monitoring (e.g. checks for incoming, processed and even live data)

## Goals

Overall, we want to make it *much easier* to add a new collection, or update an existing one.  We can achieve this by having:

* one repository for *all* "content" related code/configuration
  * *should* make for coherent pull requests/changes, rather than having commits scattered across several git repos as is the case currently
  * all inclusive versioning of collection definitions
* reduction in redundancy
  * technology specific configuration could be generated from a single configuration file, e.g. the collection name would be specified in **only one place** and could therefore be easily changed
* an abstraction over different technologies (related to the previous point)
  * more "human-readable"/simplified configuration
  * technology agnostic - e.g. could switch from talend to something else more easily :smile:

## Migration Path

Going from how things are currently to what is envisaged here would be a big job, but it can be done in a number of steps:

1. merge all git repos in to one, with a top-level directory corresponding to each
1. re-organise to have things grouped by collection (as prototyped here), and then by technology. This would require scripts to generate geoserver directory hierarchy etc
1. factor out and simplify common configuration between different technologies

*Note: this example repo is as described in (2) in terms of organisation, but without the scripts and full set of collections.*
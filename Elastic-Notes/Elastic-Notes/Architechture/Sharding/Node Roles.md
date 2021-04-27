# Node Roles
Master-eligible
---------------

denotes that a node may be elected as the cluster's master node

A master node is responsible for creating and deleting indices, among other nodes

a node with this role is not automatically made master node

*   unless there are no other master-eligible nodes

for prod/large clusters it's best to have a dedicated master 

    node.master: true|false

Data
----

enables node to store data

storing data includes performing queries related to that data suchas search queries

useful for having dedicated master nodes used as part of config-in dedicated master nodes

*   ie master serves requests and data nodes hold data and run queries

    node.data: true|false

Ingest
------

enables node to run ingest pipline

ingest pipelines are a series of steps/processors that are prerfirmed when indexing documents

*   processors may manipulate documents (eg resolving an IP to lat/lon)

    node.ingest: true|false

Machine learning
----------------

`node.ml` id's a node as to run machine learning jobs

`xpack.ml.enabled`enables or disbles the machine learning API for the node

useful for running ML jobs that don't affect other tasks

    node.ml: true|false
    xpack.ml.enabled: true|false

Coordination 
-------------

coordinates the distribution of queries and the aggregation of results

Like a router to data nodes

configed by disabling all other roles 

    node.master: false
    node.data: false
    node.ingest: false
    node.ml: false
    xpack.ml.enabled: false

Voting-only
-----------

rarely used

a node with this role will participate in the voting for a new master node but nod cannont be elected

    node.voting_only: true|false

### When to change roles of roles

\-useful for latge clusters

typlically done when optimizing the cluser to scale 

you will often change other things first

eg number of nodes, shards etc

### `node.role` values from `_cat/nodes?v`

`**noe.role**`**,** `**r**`**,** `**role**`**,** `**nodeRole**`

(Default) Roles of the node. Returned values include:

*   `c` (cold node)
*   `d` (data node)
*   `h` (hot node)
*   `i` (ingest node)
*   `l` (machine learning node)
*   `m` (master-eligible node)
*   `r` (remote cluster client node)
*   `s` (content node)
*   `t` (transform node)
*   `v` (voting-only node)
*   `w` (warm node)
*   `-` (coordinating node on
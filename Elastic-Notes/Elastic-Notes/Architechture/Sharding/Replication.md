# Replication
Replication is supported and enabled by default

How does it work
----------------

replication is configured at the index level

Replicas works by creating copies of shards, ("replica shards")

a shard that has been replicated is called a primary shard

a primary shard and its replica shards are referred to as a replication group

replica shards are a complete copy of a shard

a replica shard can serve search requests exactly like its primary

the number of replicas can be configured at index creation 

#### NOTE:

Only useful in clusters with more than one node as if there is only one node replicating the data is not doing anything for you

#### Choosing the number of replica shards

How many replica shard are ideal depends on the use case

is the data elsewhere? is it OK for data to be unavailable

In production: should always replicate at least once

### Performance enhancements

adding more replicas can increase throughput as the replicas are searched in parallel and Elasticsearch will route request to the best shard for performance

### Example:

![](api/images/DiKTRQs8oIaD/image.png)

![](api/images/OGZrJYwz2kIM/image.png)

#### Snapshots

are supported are point in time backups where replication is focused on availability and performanc
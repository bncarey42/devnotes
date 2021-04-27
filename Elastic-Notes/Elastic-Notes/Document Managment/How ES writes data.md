# How ES writes data
walks through same routing steps as reading

instead of finding most available shard writing is always pointed to the primary shard

the primary shard then validates and forwards the update to the replica shards in parallel 

If a write to a replica shard fails - a highly reductive overview:
------------------------------------------------------------------

### Primary terms- 

*   a way to distinguish between old and new primary shards
*   primary term is essentially a counter for the number of times the primary term changes 
*   primary term is appended to write operations

### Sequence numbers

*   appended to write operations with the primary term
*   essentially a counter that is incremented for each write operation
*   the primary shard increases the sequence number
*   lets a shard know what order operations occured

Primary terms and sequence numbers are key when ES needs to recover from a primary shard failure

enables ES to more efficiently figure out which write operations need to be applied

For large indices, this process is really expensive

to sped this up 

### Global & local Checkpoints 

*   essentially sequence numbers
*   each replication group has a global checkpoint
*   each replica shard has a local checkpoint
*   Global checkpoints
    *   the sequence number that all active shards within a replication group have been aligned at least up to
*   Local Checkpoints
    *   the sequence number for the last write operation that was perf
# Understanding Routing
Routing: the process of resolving a shard for a document

ES uses the folloing formula to calulate what shard the document should be stored

    shard_num = hash(_routing) % num_primary_shards

![](Understanding%20Routing/1_image.png)

Routing is therefor 100% transparent This makes Elasticsearch easier to use and learn

It is _possible_ change this default routing strategy (covered later) but this default routing strategy ensures that data is evenly distributed across all data nodes

![](Understanding%20Routing/2_image.png)

Each document is stored with metadata this is where `_routing` comes from (though it is not displayed here unless it is defined explicitly)

EX: the non-\_source fields in the object

    {
      "_index" : "products",
      "_type" : "_doc",
      "_id" : "100",
      "_version" : 18,
      "_seq_no" : 27,
      "_primary_term" : 1,
      "found" : true,
      "_source" : {
        "name" : "Toaster",
        "price" : 79,
        "in_stock" : 4,
        "instock" : 3
      }
    }
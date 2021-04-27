# Queries
    //create index with 2 shards and 2 replicas
    PUT products
    {
     "settings": {
       "number_of_shards": 2,
       "number_of_replicas": 2
     }
    }
    //get teh shards for the products index
    GET _cat/shards/products?v
    
    POST products/_doc/100
    {
     "name": "foobar",
     "price": 69.69,
     "instock": 5
    }
    //search for a product
    GET products/_search
    {
     "query": {
       "match": {
         "name": "garbleflange"
       }
     }
    }
    //get product at _id 100
    GET products/_doc/100
    
    //update a value
    POST products/_update/100
    {
     "doc": {
       "instock": 3
     }
    }
    //add a field to the document at _id 100
    POST products/_update/100
    {
     "doc": {
       "tags": ["electronics","baz"]
     }
    }
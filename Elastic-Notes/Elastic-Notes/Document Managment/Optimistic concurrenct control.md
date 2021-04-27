# Optimistic concurrenct control
prevent overwriting documents inadvertently due to concurrent operations

there are many scenarios in which this can happen

 eg handling concurrent requests to a website

![](Optimistic%20concurrenct%20control/image.png)

### To Solve:

the old way: include the version number on the request e.g. `POST /products/_update/100?version=1`

\-works well in most cases 

the new way is to use primary terms and sequece numbers

when retrieving a document includes pt's and sn's

    POST products/_update/100?if_primary_term=1&if_seq_no=28
    {
      "doc": {"in_stock": 124}
   
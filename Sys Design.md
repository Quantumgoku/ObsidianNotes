---
created: 2026-09-20T22:03
updated: 2026-10-05T11:44
---
NFR almost always trade off against each other: strong consistency vs low latency, high availability vs simplicity.

Learn Back-of-envelope estimation

when designing apis, be precise about data model like note title content string, id a string and all, status codes for response, deep delve in sanitization, authentication



Application response time directly depends on the data source and underlying database response time.
DB selection and DB modelling is imp
structured data should be stored in RDBMS
and unstructured data should be stored in NoSQL data store like Mongo DB cassandra

Questions estimates help:
-> how much space would it take to store the contents of 100M write requests?
-> how much space for storing the content of day 1M web pages(web crawlers)
-> What if we substitute each word with an integer index?
-> how many machines of 512GB storage would it fit?
-> which databse can be the best fit?


Memorizing Tip:
1M req per day with 1 kb is 1gb/day and 365 gb/year

single char = 2bytes
long/double = 8byte
resolution of image = 300kb
good resolution image = 3mb
video for streaming 100 mb/min



[[Mock Interview]]

[[kafka]]

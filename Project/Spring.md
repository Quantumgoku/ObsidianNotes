---
created: 2026-01-19T23:35
updated: 2026-10-05T11:39
---
equals and hashCode must be consistent to prevent data corruption, duplicate keys and silent retrieval failures in hash-based collections.

If 2 obj are considered equal(equals()== true) but generate diff hashcodes, hash-based collections break in 2 main waus:
-> Duplicate elements in a hashset/hashmap, equal objects but diff hash codes if contract broke, but hashset contains unqiue data
-> silent retrieval failures

Whenever you override the `equals()` method to define logical equality based on fields (like an `id` or `email`), you **must** override `hashCode()` using the exact same fields. This ensures that equal objects always route to the exact same bucket. 

[[Security]]


PUT method -> typically replaces the resource representation and is idempotent
PATCH method-> partially modifies a resource


HTTP status codes :
200 - success
201 - resource created
204 - success no res body
400 - bad req
401 - unauthenticated
403 - authenticated but not authorized
404 - resource not found
409 - conflict
429 - too many req
500 - server error
502 - bad gateway
503 - svc unavailable
504 - gateway timeout
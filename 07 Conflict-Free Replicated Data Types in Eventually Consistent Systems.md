Conflict-Free Replicated Data Types in Eventually Consistent Systems
====================================================================
Rochard Shaw, Basho

What is Riak?
-------------
* distributed key-value store
* buckets + keys and values
* REST + Protobuf clients (lots of official and unofficial language bindings for that)
* Data is not sharded, but distributed via *consistent hashing*
* self healing
* default distribution mode: 3 copies of data

Conflict resolution problem (after network partitions)
------------------------------------------------------
Techniques available in Riak:

* LWW (last write wins) -> obvious consistency problems, if multiple keys are changed together!
* Siblings:
  - Riak returns HTTP 300 and presents all *siblings* and client can/must choose which one should be used
  - brittle and error prone for client!
* New: CRDTs (cf. [INRIA paper][inria])

Available Data Types:

* Counters (since Riak 1.4)
* G-Sets and Maps (Q4 / 2013)
* Booleans (Q4 / 2013)

Maths behind this
-----------------
* Monotonic functions
* Set lattices
* Bounded lattices
* Vector clocks

Types
------

* G-Counter ('G' = 'grow only')
* PN-Counter - incrementable + decrementable (implemented internally via 2 G-Counters)
* G-Sets: sets without *remove* operation
* Maps

Use Cases
---------
* Counters
* *Like* buttons

Resources
---------
* [Counters in Riak 1.4](http://basho.com/counters-in-riak-1-4/)
* [Riak CRDT Cookbook/Tutorial](https://github.com/basho/riak_crdt_cookbook)


[inria]: http://hal.upmc.fr/docs/00/55/55/88/PDF/techreport.pdf



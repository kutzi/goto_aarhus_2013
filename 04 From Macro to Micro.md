From Macro to Micro - How big should your Service be?
=====================================================
Sam Newman

* internal representation serialized and send over the wire certainly **is** tight coupling
* Bounded context: 'A specific responsibility enforced by explicit boundaries'
* Coupling via DB schema is bad
  - Use [SchemaSpy](http://schemaspy.sourceforge.net/) to find couplings in DB
  - Integrate via API!
* 'Country Code tables are the StringUtils of the database'

How small should my services become?
------------------------------------

Cf. the UNIX way: small programs interacting via streams of texts

Eric Raymond: [The 17 Rules of UNIX](http://en.wikipedia.org/wiki/Unix_philosophy#Eric_Raymond.E2.80.99s_17_Unix_Rules)
E.g:

* Rule of Modularity
* Rule of Simplicity
* Rule of Parsimony
  - if your board knows about the name of a single service, it's too big
  - easier to throw away / rewrite

So how big, then?

* So small that I can fit the concepts in my head
* '200 lines of code' [CK: not really realistic IMHO]

So, is the communication cost between all these small service no performance problem?
Yes maybe, but remember:

* performance is not the most important thing!
  - [CK: scalability is usually more important; achieving business goals most!]
* Measure before you say, it's slower!

More problems/challenges with micro-services:

* No binary decision if platform is *up* or *down*. More fuzzy
* no big bang solution when going from macro to micro. Introduce micro services *incrementally and learn from it*!

Summary
-------
* Identify bounded contexts
* Understand the cost of change
* This is an incremental journey!
* While size is important, the number of services is often a limiting factor
  - [CK: I'm not sure, if I remember, what was actually meant with this - maybe that the administration/communication overhead will become a problem when I have thousands of services?]

Q & A
-----
* Prefer to let clients talk to the service directly: no coordinating service layer!

Resources
---------
* Presentation [Designing for Rapid Release](http://vimeo.com/47515968)
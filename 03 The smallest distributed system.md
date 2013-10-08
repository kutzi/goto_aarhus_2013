The smallest distributed system
===============================
Matthias Meyer, Travis CI

* 'Hub' became central component in Travis -> bottleneck
	- similar for RabbitMQ, but less a problem
* GitHub API proved as not always reliable
  - doesn't answer all the time
  - weird error codes
  - undocumented features changed without warning [CK: we'll that's why they weren't documented!]
* Treat external resources as: 'can fail *any* time'
  - Use timeouts + retries + exponential back-offs for retries!
* 'Big ball of mud' in Travis CI core
* Reliance on ordered message dispatching (RabbitMQ) severely limited scalability
  - so make the order part of the messages, so that order can be restored later in the DB layer
* Append-only writes are much faster than updates
* Use simple 'clock counters' for messages
* with all these changes the 'logs' component went down to ~30 lines of code
* Travis CI: currently 45000 builds / day
* Give each request an UUID so you can trace it easily in logs!

Resources
---------
* Leslie Lamport: [Times, Clocks and the Ordering of Events in a Distributed System](http://research.microsoft.com/en-us/um/people/lamport/pubs/pubs.html#time-clocks)
* [Paxos](http://en.wikipedia.org/wiki/Paxos_(computer_science)) (Consensus solving protocol)
* [Commutative Replicated Data Types](http://highscalability.com/blog/2010/12/23/paper-crdts-consistency-without-concurrency-control.html)
* [DSRG reading group at MIT](http://pdos.csail.mit.edu/dsrg/)
* Michael Nygard: Circuit Breaker and BulkHead patterns (e.g. <http://www.infoq.com/interviews/Building-Resilient-Systems-Michael-Nygard>)
* 'Distributed Clocks'?
* 

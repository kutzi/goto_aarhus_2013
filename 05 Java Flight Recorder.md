Java Flight Recorder
====================
Rickard Bäckman, Oracle

What is it?
-----------
* Event recording
* Profiling
  - existing profilers use either Safepoints or Bytecode instrumentation -> skewed results!
* 'After the fact' reports
* Less than 3% overhead in runtime
* Only using information which is already there in the JVM
* *Java Mission Control* as GUI
* Can be enabled/disabled at runtime
  - startable via Mission Control or jcmd utility 
* Configurable/filters to concentrate on the relevant info resp. reduce overhead
* Commercial license [CK: starting at 5000$ / CPU] for production
 
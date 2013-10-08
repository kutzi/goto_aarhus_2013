Architecural Simplicity through events
======================================
Russ Miles

* Challenge: build the 'right thing' the 'right way'!

Axioms
------
* 1st role of software is to be useful
* Human comprehension is king
* [Mechanical sympathy](http://mechanical-sympathy.blogspot.de/) is queen
* Software is Research (!) and Development. The former is often being forgotten!

Simplicity
----------
* Simple software is SW which can change/adapt to changing requirements
  - This does specifically *not* mean sw which is so configurable to be adaptable to 'all possible' requirements during runtime!
* Why do we don't write simple SW?
  - constant change in requirements
  - Bored by business problems?

Component design
----------------
 O.R.E.: Organise -> Reduce -> Encapsulate

Organise
--------
* Where should a component be situated?
* Hexagonal / life preserver architecture
  - Traditional layers don't help to answer the question where a component belongs!
* Component entanglement prevents adaptability
   - Test: how many files need to be changed for a simple requirement chnage?

Ports + Adapters
----------------
* 'Core' vs. 'Integration' domain
* Extract/encapsulate side effects into the integration domain!
* Event domain/'Glue domain'
  - immutable events
  - temporaral concerns are encapsulated here!
* Typed events still are a type coupling, so next step is to go to immutable data as the communication format
	- apply postel's law (be liberal in what you accept ...) - where possible
	  * Caveat: testing must be extended a lot!
	  * should be only used for inter-domain communication! (For intra-domain type coupling is fine)
* Inter-domain code duplication is okay!


Resources
---------
* Martin Fowler: [Strangler application pattern](http://martinfowler.com/bliki/StranglerApplication.html)






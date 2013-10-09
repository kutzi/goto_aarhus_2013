DevOps culture and practices to create flow
===========================================
Jez Humble, Thoughtworks


Problem: there is no visible *production line* in SW developement - i.e. products flowing down the conveyor belt

Think of requirements/change requests/ideas as the products flowing through your line!

Problem in 'agile' companies:

    Requirements: Study+Approval; Design   - Not Agile (*Water*)
            |
            v
    Implementation                         - Agile (*Scrum*)
            |
            v
    Intergration QA; Production            - Not Agile (*Fall*)

-> *Water-Scrum-Fall*

* *Jidoka* = automation + people = autonomation
  - stop the production line if there is a problem!
  - production line in (some) Toyota factories are stopped 3000 / day!
* If builds are regularly broken for > 10 minutes, that's not CI!
  - Revert changes more often!
  - It's selfish if you don't revert your changes, when they break the build for everyone!
* Everone should commit to trunk at least once a day!
  - always think in small steps!
  - checking into trunk is *communication* with other devs!

How long to bring something live?
---------------------------------
* [Little's law](http://en.wikipedia.org/wiki/Little's_law)
* Cumulative burn-up charts
* Reduce WIP to improve *time-to-production*
* Cycle time is inversly proportional to utilisation of resources (i.e. developers)
  - focussing on cycle time will decrease utilisation!

Improvement Kata
----------------
* Going from current condition to target condition
* *Innovate* on how to get there (every day)
* Plan-Do-Check-Act ([PDCA](http://en.wikipedia.org/wiki/PDCA)) cycles

Miscelleaneous
--------------
* HP: business was so desperate how to improve, so they even asked the devs ;-)
* Get feedback as fast as possible, get rid of integration phase!
* Filter out bad ideas quickly

Resources
---------
* Paul Graham: [Black Swan Farming](http://www.paulgraham.com/swan.html)

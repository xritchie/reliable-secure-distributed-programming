Notes:
------

Events:
-------
	```
	<Event | Attributes, ...>
	```
	- to disambiguate between events of the same name we use
	```
	<co, Event | Attribute, ...>
	```
	- co -> component defining the event

	- Events from the same component are processed n the order in which they are triggered
 	- FIFO order is only enforced on events among local components in a given stack.
 	- We assume that ever process executes code triggered by events in a mutal exclusive way
 	- Events in the same processes are not handled concurrently

 	**Event Handling and Triggering**
 	```
 	upon event <co1, Event1 | Attr1, Attr2, ...> do
 		do something;
 		trigger<co2, Event2 | AttrA, AttrB, ...>
 	```

 	**Local Conidition Handling**
 	- do not respond to external events originating from different components;
 	```
 	upon <coniditon> do
 		do something;
	```

	**External Events, Local Condition**
	- Events from another module can also be qualified with a conidtion on local variable.
	```
	upon event <co, Event | attr, ...> Such that <Condition> do
		do something;
	```
	- An algorithm that uses conditional event handlers relies on the runtime system to buffer external events until the conidition on internal variables becomes satisfied.

APIs
-----

	- **REQUESTS** - events are sused by components to invoke a service at another component or signal a conidition to another component.
	- **INDICATION** - aer used by a component to deliver information to signal a condition to another component.


Types of Algorithms:
--------------------
1. fail-stop algorithms, designed under the assumption that processes can fail by crashing but the crashes can be reliably detected by all the other processes;
2. fail-silent algorithms, where process crashes can never be reliably detected;
3. fail-noisy algorithms, where processes can fail by crashing and the crashes can
be detected, but not always in an accurate manner (accuracy is only eventual); 4. fail-recovery algorithms, where processes can crash and later recover and still participate in the algorithm;
5. fail-arbitrary algorithms, where processes can deviate arbitrarily from the pro-
tocol specification and act in malicious, adversarial ways; and
6. randomized algorithms, where in addition to the classes presented so far, pro-
cesses may make probabilistic choices by using a source of randomness.
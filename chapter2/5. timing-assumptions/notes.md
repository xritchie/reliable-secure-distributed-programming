- asynchronous distribution system comes down to not making any timing assumption about procsses and links.
- **logical time** - measuring the passafe of time based on the transmission and delivery of messages such that time is defined with respect to communication. (resulting notion of a clock is called **logical clock**)


Simple Logical Clock
---------------------
1. every proces p, keep a logical clock lp, initially set to 0
2. whenever an event occurs at process p, the logical clock lp is incremented by one unit.
3. when a process send a message, it adds a timestamp to the message with the value of its logical clock at the moment the message is sent. the timestamp of an event e is denoted by t(e)
4. When a process p receives a message m with tiemstamp tm, process p increments its logical clock in the following way lp := max{lp,tm} + 1

- causality conidtion - happend before relationship - e1 -> e2 => t(e1) < t(e2)


Synchronous System
------------------
- Step - gathers the delivery of a message / local computation / sending of a message
- Synchronous Computation - There is a known upper bound in processing delays. That is the time taken by any process to execute a step is awlays less than this bound.
- Synchronous communication - There is a known upper bound on message transmision delays.

Synchronous Physical clocks
----------------------------
Every processed is equipped with a local physical clock. there is a known upper bound on the rate at which the local physical clock deviates from a global real-time clock.

Syncrhonous Distributed System Services
----------------------------------------
- Timed failure detection: Every crash of a process may be detected within bounded time. (Heartbeat used to detect crashed processes)
- Measure of transit delays: It is possible to get a good appricimation of the delays of messages in communication links.
- Coordination based on time: One can implement a lease abstraction that provides the right to execute some action during a fixed period of time.
- Worst case perforamnce: By asusming a bound on the number of faults and on the load of the system, it is possible to derive worst-case response times for any given algorithm.
- Synchronized clocks - A synchronous system makes it possible to synchronize the clocks of the different processes in such a way that they are never apart by more than some known constant δ, called the clock synchronization precision. In practice, δ is always greater than zero and events within δ cannot be ordered.

Partially Synchrony
--------------------
- for most systems that we know of, it is relatively easy to define physical time bounds that are respected most of the time. There are however periods where the timing assumptions do not hold.
- One way to capture partial synchrony is to assume that the timing assumptions only hold eventually, without stating when exactly.

Failure Detector
----------------
failure detectors encapsulate the timing assumptions of a synchronous system and failure detector that encapsulate the timing assumptions of a partially synchronous system.

Advantages of such failure detectors vs introducing timing assumptions
- simplicity initially intorduced in the processes and links is preserved
reason about the behaiour of a failure detector using axiomatic properties with no explicit reference to physical time.



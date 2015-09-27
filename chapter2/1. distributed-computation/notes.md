Processes and Messages
----------------------
- Π -> Set of process inside of a system
- Π is static and does not change
- All process in Π know of each other and their identities
- self denotes the name of the process executing the code
- messages are uniquely identified by their original sender process using a sequence number or a local clock, together with the process identifier.
- Assume that all messages that ever exchanged by some distributed algorith are unique

Automata & Steps
----------------
- Assume the existence of a global clock
- clock global and linear notion of time that regulated the execution of the algorithm
- steps of the process are executed according to ticks of the global clock
- Even if two steps are executed at the same physical instant, we view them as if they were executed at different times of our global clock.
- correct proccess - executed an invite number of steps in an automaton
- Process Step - consist of receiving (sometimes we also say delivering) a message from another process (global event), executing a local computation (local event), and sending a message to some process (global event).
- Sometimes a prcess has no message to receive or send but has some local computation to perform this is captured simply by assuming that messages can be nill
- It is important that the interaction between the components of one process is viewed as local computation and not as communication, altough they look syntactically the same.
- Self Processes -> Local Process = Computation Step
- Self Processes -> Remote Process = Communication Step
- We shall assume Determinisitic Algorithms - Event + Current State -> Output State
- Random/Probabilistic Algorithms - process may use a local random source, Non-determinisitc to a point 
- Safety - safety properties state that the algorithm should not do anything wrong.
- Liveness - is a property of distributed system execution such that, for any time t, there is some hope that the property can be satisfied at some time t' >= t.
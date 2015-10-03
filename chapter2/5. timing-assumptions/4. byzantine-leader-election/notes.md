Byzantine Leader Election
--------------------------
- we assume that the leader should perform some actions according to an algorithm withing some time bounds.
- if the leader peforms wrongly or exceeeds the allocated time before reaching this goal then other process detect this and report it as a failure to the leader detector.
- every leader is given progressively more time than its predevessors to achieve its goal.
- <Complain | p> event - every process may complain against the current leader p by triggering this event.
- we assume that every correct process successively increases the time between issuing complaints.

Rotating byzantine leader detection
-----------------------------------
- N - number of processes in the system (the size of Π)
- assumption N > 3f
- Round - the era under which a leader is under control.
- The algorithm maintains a continously increasing round number and deterministically derives the leader from it.
- The leader in a round r is simply the process p whose rank is r mod N
- whenever a process received more than 2f complaints message against the current leader it switches to the next round.
- when a prcesses receives more than f Complaint messages but has not sent a complaint message itself in the current round, it joins the complaining process and also sends a complaint message. 
    - Byzantine processes alone cannot provoke a leader change
    - once a correct process siwtches to the the next round, every other correct proxess eventually aslo witches to that round.
- #(S) denotes the number of none ⊥ entries in list S, respectively.
- [x]^N -> N-vector [x,...x] -> #([x^N]) = N
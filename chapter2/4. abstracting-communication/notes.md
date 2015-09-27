Link Failure
------------
- A simple way to overcome the inherent unreliability of the network is to keep on retransmitting messages until they reach their destinations.
- <Send> - REQUEST event to send a message
- <Deliver> - INDICATION event that delivers a message
- A message is typically received at a given port of the network and stored within some buffer, and then some algorithm is executed to make sure the properties of the required link abstraction are satisfied, before the message is actually delivered. 
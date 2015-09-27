Hash Functions
--------------
A cryptographic hash function maps a bit string of arbitrary length to a short, unique representation. The functionality provides only a single operation H; its invocation takes a bit string x of arbitrary length as an input parameter and returns a value h, which is a short bit string of fixed length in practice.

A hash function is collision- free in the sense that no process, not even one subject to arbitrary faults, can find two distinct values x and x′ such that H(x) = H(x′).

Message Authentication Codes (MACs)
-----------------------------------
It is based on a shared symmetric key, which is known only to the sender and to the receiver of a message, but to nobody else. For a message of its choice the sender can compute an authenticator for the receiver. Given an authenticator and a message, the receiver can verify that the message has indeed been authenticated by the sender. It is infeasible for any other entity than the sender and the verifier to come up with a message that was never authenticated and to produce an authenticator that the receiver accepts as valid during verification.

- every ordered pair of processes in Π × Π is associated with a separate MAC
- Operations: authenticate(p,q,m) and verifyauth(p,q,m,a)
- p -> receiver processes
- q -> receiver processes
- m -> bit string
- a - returns authenticator response

Digital Signatures
-------------------
Physical realizations of digital signatures associate a public-key/private-key pair with an entity. The private key is given to the entity and must remain secret; the public key is accessible to anyone. With the private key the entity can produce a signature for a statement of its choice. The public key is associated with the identity of an entity, and everyone with access to the public key can verify that the signature on the statement is valid.

It is infeasible for any entity that does not know the private key to come up with a statement that was never signed and to forge a valid signature on it.

A signature scheme is more powerful than a MAC in the sense that authenticated messages can be verified by all entities and relayed even by untrusted entities.

- Operations - sign(p,m) & verifysig(p,m,s)
- p -> processes identifier
- m -> bit string
- s -> signature
- c1 || c2 || .. || ck -> concatentation of k bit strings
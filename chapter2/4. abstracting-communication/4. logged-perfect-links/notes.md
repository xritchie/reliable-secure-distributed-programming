Logged Perfect Links
---------------------
- Crash-recovery process abstraction
- crash recovery process abstraction may use stable storage which is accessed through store and retrieve operations.
- alternatve way for delivering an output in the crash-recovery model; it consists of logging the output in stable storage.
- Instead of triggering an event to deliver a message the module writes the message to a local log, implemented by a variable in stable storage
- Variables can also be accessed by the modules in the layer above through a retrieve operation.
- To notify the layer above of the delivery the module triggers an event <Deliver | identifier> that contains the name identifier off the logging variable in stable storage.
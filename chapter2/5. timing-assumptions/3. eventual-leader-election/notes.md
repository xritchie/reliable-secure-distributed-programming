Specifications
- eventual-accuracy
- eventual agreement
- leaders may change in an arbitrary manner and for an arbitrary period of time
- many leaders might be elected during the same period of time wihtout having crashed
- Process p is said to be trusted afterward until an indication event with another leader process occurs.


Elect Lower Epoch
------------------
epoch number - an interger variable contianing how many times the process crashed and recovered.
- goal elect the  active process with the lowest epoch number as a leader
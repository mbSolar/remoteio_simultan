When remoteio proceeds 2 pins, the second pin must wait until the first one has made his work on the server. This may take time, if the first pin has a long timer and the second pin cannot start its work.
A pin blocks itself in the same way. In this modification of remoteio, different pins can work simultaneously. If a pin has two tasks and the second one is asked to start before the first one has finished,
the second one interrupts the first one.
The main modifications are the use of 
  1. a list of maps, that allows sending of tasks of several pins to the server
  2. an own thread for each pin for treating
  3. thread safe queues for each pin as input to the pin-specific threads

Further, the internal pin numbering is 'b', by the aid of a conversion dictionary. This allows to suppress the establishing of the sam pin two times by different representations by 'b' and 'g'
The syntax to operate the pins is the same as that of remoteio.

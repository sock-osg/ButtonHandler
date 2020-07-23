* For Arduino is not necessary to connect a resistor pull up because all the I/O have an internal one.

* For NodeMCU it is necessary because this micro-controller doesn't have this feature, this is the diagram for this case:

---
Button not pressed:

             VCC
                |
           20K | |
               | |
       pull-up |_|
                |
                |                 _____
      input ––––*––––––o–––––––––o     o––––– GND
                      pin       released
                                 button
---

---
Button pressed:

               VCC
                |    :
           20K | |   :
               | |   :
       pull-up |_|   :  some current flows
                |     `- - - - - - - - - ->
                |
      input ––––*––––––o–––––––––o–––––o––––– GND
                      pin        pushed
                                 button
---

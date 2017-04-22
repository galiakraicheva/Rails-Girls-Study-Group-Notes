# HTTP Verbs

**Context:** In the Michael Hartl tutorial there is a reference to REST. Chapter 2 speaks about HTTP Verbs. Here are more explanations about it.  

In short HTTP verb is a name given to a part of the HTTP protocol. 

Questions: 
  1. What is an HTTP protocol? 
  2. What are the other protocols? 
  3. What is their purpose?
  
 Answers: [How the Internet Works](https://github.com/galiakraicheva/Django-Girls-Rails-Girls-Continuation-Materials/blob/master/how_does_the_internet_work.md)
 
 A lot of people in the world write software. Every person has a different understanding how to write software. Different software should be able to work together and be able to exchange data. This is why people have agreed on protocols so that their software can speak to other software and exchange data. 
 
 In order for computers to communciate, they need to be able to exchange info about their state. If they are connected by physical cable, this is info about voltage for a moment in time. If it is wifi, this is info about radio waves. If the voltage is high enough for a given period of time, it is 1, of there is low voltage, it is 0. All data exchanges on the Internet is exchanged by transmitting info about 0s and 1s. So for us to transmit a file on the Internet, it is broken into 0s and 1s and these 0s and 1s travel through the cable to reach the computer on the other side. In this process, we have to make sure we don't lose 0s and 1s, they come in the same order and they are put together correctly. Unfortunatelly, dealing with 0s and 1s is very difficult for humans to understand. That is why people have created more and more levels of abstractions to make it easier to understand and controll the transmission process. 
 
 One popular name, given to these levels of abstraction is OSI model and it says that there are 7 layers on the Internet. 
 
 Here are some of them: 
 
 APPLICATION LAYER: the most human-readable
 HTTP/SNTD/...: here is the famous HTTP protocol
 TCP/UDP

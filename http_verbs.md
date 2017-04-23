# HTTP Verbs

**Context:** In the Michael Hartl tutorial there is a reference to REST. Chapter 2 speaks about HTTP Verbs. Here are more explanations about it.  

In short HTTP verb is a name given to a part of the HTTP protocol. 

Questions: 
  1. What is an HTTP protocol? 
  2. What are the other protocols? 
  3. What is their purpose?
  
 Answers: [How the Internet Works](https://github.com/galiakraicheva/Django-Girls-Rails-Girls-Continuation-Materials/blob/master/how_does_the_internet_work.md)
 
 A lot of people in the world write software. Every person has a different understanding how to write software. Different software should be able to work together and be able to exchange data. This is why people have agreed on protocols so that their software can speak to other software and exchange data. In order for two softwares to be able to speak to each other, they should follow standards (protocol) which are predefined.  
 
 In order for computers to communciate, they need to be able to exchange info about their state. If they are connected by physical cable, this is info about voltage for a moment in time. If it is wifi, this is info about radio waves. If the voltage is high enough for a given period of time, it is 1, of there is low voltage, it is 0. All data exchanges on the Internet is exchanged by transmitting info about 0s and 1s. So for us to transmit a file on the Internet, it is broken into 0s and 1s and these 0s and 1s travel through the cable to reach the computer on the other side. In this process, we have to make sure we don't lose 0s and 1s, they come in the same order and they are put together correctly. Unfortunatelly, dealing with 0s and 1s is very difficult for humans to understand. That is why people have created more and more levels of abstractions to make it easier to understand and controll the transmission process. 
 
 One popular name, given to these levels of abstraction is OSI model and it says that there are 7 layers on the Internet. 
 
 Here are some of them: 
 
 Application Layer (HTTP/...): the most human-readable, this is where the HTTP protocol "lives"
 
 Session Layer and Presentation Layer
 
 Transport (TCP/UDP)
 
 Network (IP) --> Which is the right machine from all machines on the Internet to transmit the info to
 
 Data Link (Ethernet) --> Which is the right machine in the one local network to send the info to
 
 Physical Impulses --> Radiowaves or electic signals
 
 
 In more details: 
 
 Physical Layer: you have a timer and a measurement of the state (the amount of voltage). So 0s and 1s are being transmitted. 
 Data Link: ensures the correct transmission between two nodes
 
 Network Layer: deals with finding the right machine, routing between different machines to reach the right one, traffic control
 
 Transport Layer: deals with the relayable transmission of packages between different machines in the network. The TCP protocol guarantees that there will be no omissions in sending the packages. It guarantees that all packages will arrive in the order they were sent in. For example, if you send an image on the Internet to another computer you expect the other person to recieve it with no missing pixels. The UDP is faster but does not guarantee that all packages will arrive. There may be some packages that get missing during transportation.
 
 Session Layer and Presentation Layer: they manage the translation between application and network formats and establishment and closure of connection.
 
 Application Layer: The application Layer is where the HTTP protocol lives. HTTP is a protocol that is used for browsers to communicate with webservers (the program, called webserver, not the machine). 
 
 
 HTTP is a text protocol, meaning that it is written in plain text. It comprises of information that tells the server where to look for a website and what is the domain of the website the browser wants. Or it can say what the response of the browser is. 
 
 If we type abv.bg in our address bar and click Enter, it automatically gets changes to http://abv.bg, which is the same as http://abv.bg(:80)
 
 http is the protocol
 
 abv.bg is the domain
 
 :80 is the port on the server
 
 
 If we type http://dir.bg:80/today?fresh=5
 
 http is the protocol
 
 dir.bg is the domain
 
 :80 is the port on the server
 
 today?fresh=5 is the path
 
 The first thing that happen is that the browser goes to a DNS client that tells the IP of the machine which hosts abv or dir.bg website. Then the HTTP request goes to the server where the abv.bg or the dir.bg website live. HTTP protocol says "go to port 80 on the server". HTTPS says "go to port 443". Let's say we have HTTP. The request form the browser goes to a server at port 80, where there should be a webserver program, like NginX. NginX understands the request. When we configure NginX at the website, we tell it what sites we have in this server. It looks something like this: 
 
 NginX
 
 {listen 80
 
  server-name dir.bg
  
  root/sites/dir.bg
  
  }
  
  
  {listen 80
  
  server-name abv.bg
  
  root/sites/old_abv.bg
  
  }
  
  So this is a list of all websites that live in the server. So when we publish our website on the web for first time, we make changes to the configuration files. 
  
  What are the rules for browser and server to speak to each other? It is through request and response. The browser sends a request as an HTTP and the server responds as an HTTP. Done! Another request and another response and so on. 
  
  Each request and response has 2 different parts: meta data/heads (obligatory) and data (optional)
  
  Sample Request from Google Chrome: 
  
  ...
    GET/today?fresh=5 HTTP/1.1
  HOST: abv.bg
  user_agent:Google Chrome
  date: .....
  accept-language:...
  cookies: user = 1.....
  
  data
  ...
  
  Let's break it down:
  ...
  GET/today?fresh=5 HTTP/1.1
  HOST: abv.bg
  user_agent:Google Chrome
  date: .....
  accept-language:...
  cookies: user = 1.....
  
  
  data
  ...  
  

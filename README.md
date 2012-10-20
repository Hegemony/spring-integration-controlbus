Spring Integration Controlbus controlling JMS inbound channel adaptor  
=====================================================================

In this project, I will demo Control Bus capability of Spring Integration, where in we can stop or start JMS inbound channel adaptors runtime as an alternative to MBean. 

To quickly see how it works,

Just test the subscriber architecture
In this project, I will demo the use of [Control Bus-Enterprise Integration Pattern](http://www.eaipatterns.com/ControlBus.html) using Spring Integration. To quickly see how it works,

* Download [activemq](http://activemq.apache.org/activemq-560-release.html)
* Start the activemq by executing <Activemq home>/bin/activemq.bat
* Create Queues called "MyQueue" and "ControlBusQueue"
* Get the latest code
* Import the maven project into STS IDE, and "Run at Server"
* Now put a message on to "MyQueue", you see the debug message on both the service activators where the messages are published
* If you want to stop the "inbound channel adaptor" to listen to the Queue, put a message "@inboundAdaptor.stop()" on "ControlBusQueue". To test it, put a message on to "MyQueue" the message is not published
* To start the adaptor, again put a message "@inboundAdaptor.start()", the earlier message is consumed.

* to JUnit test this, run "mvn test"

Refer this [blog](http://krishnasblog.com/) for more details on the above flow.

Feel free to modify this code and use it for your need. 

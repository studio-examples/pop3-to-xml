# Importing an attached csv file using the POP3 connector


This example shows you how to use the POP3 connector to facilitate information transfer through email. It also illustrates how you can use the datamapper to transform a CSV file to XML.

### Assumptions

This document describes the details of the example within the context of Anypoint™ Studio, Mule ESB’s graphical user interface (GUI). This document assumes that you are familiar with Mule ESB, [Datamapper](http://www.mulesoft.org/documentation/display/current/Datamapper+User+Guide+and+Reference) and the [Anypoint Studio interface](http://www.mulesoft.org/documentation/display/current/Anypoint+Studio+Essentials). 

### Example Use Case

In this example a CSV file containing sample sales data which has been received as an attachment in a gmail inbox is imported using the POP3 connector. The Datamapper then converts the CSV file to the XML format. The logger then logs this data on the studio console.

### Set Up and Run this Example

1.  **Open** the project in the studio interface

2. In the Package Explorer, navigate to src/main/resources and **edit common.properties** as follows:

           pop3.host=pop.gmail.com
           pop3.port=995
           pop3.user=senderemailaddress%40gmail.com
           pop3.password=sender_password
    
3. **Run** the project as a Mule application

4. Navigate to src/main/resources and use any email address to **send the 'input.csv' file as an attachement**  to senderemailaddress%40gmail.com


5. If you have configured and run this example correctly, the csv file should appear in the xml format in the studio console. The log message should be similar to what is show below:

        INFO  2014-07-07 16:49:09,973 [[pop3-to-xml-master].POP3.receiver.01] org.mule.api.security.tls.TlsPropertiesMapper:         Defaulting mule.email.pop3s trust store to client Key Store
        WARN  2014-07-07 16:49:09,988 [[pop3-to-xml-master].POP3.receiver.01] org.mule.api.security.tls.TlsProperties: File         tls-default.conf not found, using default configuration.
        INFO  2014-07-07 16:49:10,706 [[pop3-to-xml-master].pop-to-xmlFlow1.stage1.02]       
        org.mule.api.processor.LoggerMessageProcessor: recieved: <?xml version="1.0" encoding="UTF-8"?>                   
        < orders>
        < order>
        < orderId>1< /orderId>
        < name>aaa< /name>
        < units>2.0< /units>
        < pricePerUnit>10< /pricePerUnit>
        < /order>
        < /orders>
        < orders>
        < order>
        < orderId>2< /orderId>
        < name>bbb< /name>
        < units>4.15< /units>
        < pricePerUnit>5< /pricePerUnit>
        < /order>
        < /orders>


### Go Further

* Read more about the [POP3 Connector](http://www.mulesoft.org/documentation/display/current/POP3+Connector)

* Read more about the [POP3 Transport Reference](http://www.mulesoft.org/documentation/display/current/POP3+Transport+Reference)

* Read more about the [Datamapper Transformer](http://www.mulesoft.org/documentation/display/current/Datamapper+User+Guide+and+Reference)







   

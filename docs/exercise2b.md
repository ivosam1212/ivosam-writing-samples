This section presents the main differences between the **Representational State Transfer (REST)** and the **Simple Object Access Protocol (SOAP)** web services.

REST and SOAP are two of the most used web services nowadays. Both provide a communication channel between clients and servers over the internet.

The following table lists the main differences between REST and SOAP:

| Topic       | REST        | SOAP |
| ----------- | ----------- | ---- |
| Style  | REST is an *architectural style*, meaning that there are principles to design a REST-like web service, not rules. | SOAP is a *protocol*, meaning that there are guidelines to follow for communicating data.  |
| Communication Protocols  | It uses the *HTTP* protocol to request and retrieve data. | It can use *HTTP*, *SMTP*, or *FTP* protocols. |
| Communication Formats | The most popular are XML and JSON formats. | It uses  *XML*  messaging  format between the client and the server. It contains a **SOAP Envelop** with a header, a body, and a fault element for errors. |
| Data cached       | Can cache data       | Cannot cache data |
| Security   | Supports **HTTPS** and **SSL**. | Built-in standard such as **WS-Security** in addition to **SSL** support. |
| Transactions       | Data-driven. It accesses a resource and requests, stores, or modifies data. | SOAP performs operations such as transferring structured information.|
| Performance | Message size is considerably lesser than SOAP messages, making REST faster to transmit data. | SOAP requires more bandwidth and resources, making it slower than REST. |

## REST or SOAP
Even though REST proves to have lighter payloads and faster responses, SOAP integrates security and reliability. 
You can use SOAP for:

- banking
- financial applications
- telecommunication services
- sensible, historical information

REST can work better for performance-driven projects, such as:

- mobile services
- chats
- lightweight web services
- scalable and flexible applications
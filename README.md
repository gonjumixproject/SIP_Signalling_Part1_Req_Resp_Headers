#  Sip Signalling Part 1 

- [What is SIP]()
- [What is Client-Server architecture]()
	* [What is User Agent / User Agent Client (UAC) / User Agent Server (UAS)]()
- [What are the Message Transport Layers ?]()
	* [TCP]()
	* [UDP]()
	* [TLS]()
	* [SCTP]()
- [SIP Request Message]()
	* [Methods]()
	* * [INVITE]()
	* * [REGISTER ]()
	* * [CANCEL]()
	* * [BYE ]()
	* * [ACK ]()
	* * [OPTIONS ]()
	* * [REFER]()
	* * [SUBSCRIBE]()
	* * [NOTIFY]()
	* * [INFO]()
	* * [PRACK]()
	* * [UPDATE]()
- [SIP Response Message]()
	* [1xx Informational Responses]()
	* * [100 Trying]()
	* * [180 Ringing]()
	* * [181 Call Is Being Forwarded]()
	* * [183 Session Progress]()
	* [2xx Success Responses]()
	* * [200 OK]()
	* * [202 Accepted]()
	* [3xx Redirection Responses]()
	* * [300 Multiple Choices]()
	* * [301 Moved Permanently]()
	* * [302 Moved Temporarily]()
	* * [380 Alternative Service]()
	* [4xx Client Errors]()
	* [5xx Server Errors]()
	* [6xx Global Errors]()
- [SIP Header Fields]()
- [Basic Call Flows]()


# Introduction to everthing
This part of the project covers SIP Understanding the Session Initiation Protocol book (author Alan B. Johnston) as well as the RFC 3261.

Best Materials about the SIP and VOIP network;

* SIP Understanding the Session Initiation Protocol book (author Alan B. Johnston)
* [RFC 3261](https://tools.ietf.org/html/rfc3261)
* [Eli the Computer Guy VOIP series](https://www.youtube.com/watch?v=2x3Ie6VZ_sg&list=PLUz96g7K7QmkOOnUkzUkvT8RcFpP08oE0)

# What is SIP

<pre>
The Session Initiation Protocol (SIP) is a signaling, presence and instant messaging protocol developed to set up, modify, and tear down multimedia sessions, request and deliver presence and instant messages over the Internet.


SIP was developed by the IETF as part of the Internet Multimedia Conferencing Architecture, and was designed to dovetail with other Internet protocols such as Transmission Control Protocol (TCP), Transmission Layer Security (TLS), User Datagram Protocol (UDP), Internet Protocol (IP), Domain Name System (DNS), and others. 


As the name implies,the protocol allows two end points to establish media sessions with each other. 

The main signaling functions of the protocol are as follows: 

• Location of an end point;
• Contacting an end point to determine willingness to establish a session; 
• Exchange of media information to allow session to be established; 
• Modification of existing media sessions;
• Tear-down of existing media sessions.

SIP is a client-server protocol of equipotent peers.
</pre>
# What is Client-Server architecture

- [x] What is Client-Server
- [ ] Add images
<pre>
The client component requests services from the server.

The server component provides a function or service to one or many clients, which initiate requests for such services. Servers are classified by the services they provide.

Clients and servers exchange messages in a request–response messaging pattern. The client sends a request, and the server returns a response.This exchange of messages is an example of inter-process communication. To communicate, the computers must have a common language, and they must follow rules so that both the client and the server know what to expect. The language and rules of communication are defined in a communications protocol. In this case, our communication protocol is SIP.

</pre>

## What is User Agent / User Agent Client (UAC) / User Agent Server (UAS)
<pre>
User Agent : A user agent represents an end system. It can be either user agent client or user agent server.
User Agent Client (UAC) : Generates requests.
User Agent Server (UAS) : Responds to the requests.  
</pre>
# Requests

- [x] Requests
- [x] Methods
- [x] Add Methods
- [ ] Create images
- [ ] Add images

<pre>
This chapter is created by using the RFC 3261. 

Request is a SIP message sent from a client to a server, for the purpose of invoking a particular operation.

SIP requests are distinguished by having a Request-Line for a start-line.

         Request-Line  =  Method SP Request-URI SP SIP-Version CRLF

A Request-Line contains a method name, a Request-URI, and the  protocol version separated by a single space (SP) character.

Example of a Request-Line:

INVITE sip:watson@bell-telephone.com SIP/2.0

In this below example;

INVITE : Method name
sip:watson@bell-telephone.com : Request-URI
SIP/2.0 : SIP-Version
</pre>
## Methods 

### INVITE
<pre>
The INVITE method is used to establish media sessions between user agents.
</pre>
### REGISTER

- [ ] Add an image for INVITE
- [ ] Add a reference for further more
- [ ] Add image for CANCEL
- [ ] Add image for BYE
- [ ] Add image for ACK
- [ ] Add image for OPTIONS
- [ ] Add image for SUBSCRIBE and NOTIFY together
- [ ] Add image for PRACK
- [ ] Add what is reliable reference for PRACK
- [ ] Add image for UPDATE

### CANCEL
<pre>
The CANCEL method is used to terminate pending searches or call attempts. 
It can be generated by either user agents or proxy servers provided that a 1xx response containing a tag has been received, but no final response has been received.
</pre>
### BYE
<pre>
The BYE method is used to terminate an established media session.
</pre>

### ACK
<pre>
The ACK method is used to acknowledge final responses to INVITE requests. Final responses to all other requests are never acknowledged. Final responses are defined as 2xx, 3xx, 4xx, 5xx, or6xx class responses.
</pre>
### OPTIONS
<pre>The OPTIONS method is used to query a user agent or server about its capabilities and discover its current availability. </pre>

### REFER
<pre>
The REFER method is used by a user agent to request another user agent to access a URI or URL resource.
</pre>

### SUBSCRIBE

<pre>

The SUBSCRIBE method is used by a user agent to establish a subscription for the purpose of receiving notifications (via the NOTIFY method) about a particular event. 

</pre>

### NOTIFY
<pre>
The NOTIFY method is used by a user agent to convey information about the occurrence of a particular event. 
</pre>

### INFO
<pre>
The INFO method is used by a user agent to send call signaling information to another user agent with which it has an established media session.
</pre>

### PRACK
<pre>
The PRACK method is used to acknowledge receipt of reliably transported provisional responses (1xx). The reliability of 2xx, 3xx, 4xx, 5xx, and 6xx responses to INVITEs is achieved using the ACK method. 
</pre>

### UPDATE

<pre>

The UPDATE method is used to modify the state of a session without changing the state of the dialog.A session is established in SIP using an INVITE request in an offer/answer manner.
</pre>

# SIP Response Message
<pre>
A SIP response is a message generated by a UAS or a SIP server to reply to a request generated by a UAC. A response may contain additional header fields containing information needed by the UAC.Or, it maybe a simple acknowledgment to prevent retransmissions of the request by the UAC. 
</pre>

## 1xx Informational Responses

<pre>
The informational class of responses 1xx are used to indicate call progress. Informational responses are end-to-end responses and may contain message bodies. The exception to this is the 100 Trying response, which is only a hop-by-hop response and may not contain a message body.
</pre>

### 100 Trying 
### 180 Ringing
### 181 Call Is Being Forwarded
### 183 Session Progress
## 2xx Success Responses
### 200 OK
### 202 Accepted
## 3xx Redirection Responses
### 300 Multiple Choices
### 301 Moved Permanently
### 302 Moved Temporarily
### 380 Alternative Service
## 4xx Client Errors
## 5xx Server Errors
## 6xx Global Errors


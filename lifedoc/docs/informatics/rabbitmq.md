# RabbitMQ
## About
TODO

* * *

## Heartbeats
* feature from AMQP 0-9-1
* ensures that the application layer promptly finds out about disrupted connecitons and unresponsive peers
* defend against termination of "idle" (when there's no activity for a certain period of time) TCP connections
### Timeout interval
[Source](https://www.rabbitmq.com/heartbeats.html)

* defines after what period of time the TCP conncection should be considered unreachable by RabbitMQ and client libraries
* in secounds (default: `60`)
* disable: `0` (not recommended)
* value is negotiated between client and RabbitMQ server at time of connection
	* if server has non-zero configuration --> client can only lower value
* client must be **configured to request heartbeats**
	* \>= `version 3.0`: broker attempts to negotiate heartbeats by default
* are sent every `timeout / 2`
* two missed heartbeats --> unreachable --> TCP connection will be closed
* client detects that RabbitMQ node is unreachable due a heartbeat --> needs to re-connect
> Setting heartbeat timeout value too low can lead to false positives (peer being considered unavailable while it really isn't the case) due to transient network congestion, short-lived server flow control, and so on. This should be taken into consideration when picking a timeout value.
* any traffic (e.g. protocol operations, published messages, acknowledgements) == valid heartbeat
	* sometimes sends heartbeat frames whether there was any other traffic, some only do it when necessary 

#### .Net
```
ConnectionFactory connectionFactory = new ConnectionFactory();
connectionFactory.RequestedHeartbeat = 60;
```
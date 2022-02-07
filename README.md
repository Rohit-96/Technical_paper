# __Messaging Queues__

## __What are Messaging Queues?__

![Message Queue](https://www.cloudamqp.com/img/blog/message-queue-small.png)

A message queue, known simply as a queue, is a named destination to which messages can be sent. Messages accumulate on queues until they are retrieved by programs that service those queues.

Queues reside in, and are managed by, a queue manager. The physical nature of a queue depends on the operating system on which the queue manager is running. A queue can either be a volatile buffer area in the memory of a computer, or a data set on a permanent storage device. The physical management of queues is the responsibility of the queue manager and is not made apparent to the participating application programs.

Programs access queues only through the external services of the queue manager. They can open a queue, put messages on it, get messages from it, and close the queue. They can also set, and inquire about, the attributes of queues.


## __Why are they used?__

* ### __Redundancy via Persistence__
Queues help with redundancy by making the process that reads the message confirm that it completed the transaction and it is safe to remove it.

* ### __Traffic Spikes__
For example, at Stackify we receive billions of messages a month. We have no way to know what our clients are going to send us. By queuing the data we can be assured the data will be persisted and then be processed eventually, even if that means it takes a little longer than usual due to a high traffic spike.

* ### __Improve Web Application Page Load Times__
Queues can be useful in web applications to do complex logic in a background thread so the request can finish for the user quickly.

* ### __Batching for Efficiency__
Batching is a great reason to use message queues. It is much more efficient to insert 100 records into a database at a time instead of 1 at a time, 100 times. Batching helps us optimize their performance by tuning the size of the transactions.

* ### __Asynchronous Messaging__
Queues can be great in scenarios where your application needs something done but doesn’t need it done now, or doesn’t even care about the result. Instead of calling a web service and waiting for it to complete, you can write the message to a queue and let the same business logic happen later. 

* ### __Decouple by Using Data Contracts__
By using a queue between different parts of your software you can decouple the hard dependencies. The format of the message in the queue becomes your data contract and anything that knows how to read that message format can be used to process the transaction. 

* ### __Transaction Ordering and Concurrency Challenges__
If 1000 people are placing an order on your website at one time, that could create some problems with concurrency and ensuring that the first order in finishes first. By queuing them up, you could then guarantee their order and control how many are even processed concurrently.

* ### __Improve Scalability__
Message queues enable you to decouple different parts of your application and then scale them independently.

* ### __Monitoring__
Message queuing systems enable you to monitor how many items are in a queue, the rate of processing messages, and other stats. 


## __What are popular tools?__

### __Some of the popular messaging queues tools are:__

* IBM MQ  
IBM MQ, formerly WebSphere MQ, is trusted worldwide to provide businesses with a secure messaging solution that rapidly transports message data between applications, systems and services.

* Apache Kafka
Apache Kafka is an open-source stream processing platform developed by the Apache Software Foundation written in Scala and Java.

* Azure Scheduler
Azure Scheduler allows you to declaratively describe actions to run in the cloud. It then schedules and runs those actions automatically.

* RabbitMQ
RabbitMQ is the most popular open source message broker, with more than 35,000 production deployments world-wide. RabbitMQ is lightweight and easy to deploy on premises and in the cloud and runs on all major operating systems. 

* Google Cloud Pub/Sub
Ingest event streams from anywhere, at any scale, for simple, reliable, real-time stream analytics.


## __What is Enterprise Message Bus?__

An enterprise service bus (ESB) is a software platform used to distribute work among connected components of an application. It is designed to provide a uniform means of moving work, offering applications the ability to connect to the ESB and subscribe to messages based on simple structural and business policy rules.

![Enterprise Message Bus working](https://cdn.ttgtmedia.com/rms/onlineImages/microservices-esb_diagram_mobile.jpg)

## __Benefits of an enterprise service bus__

Because an ESB controls the way work moves, it makes it easy to change components or add additional components to an application. It also makes for a convenient place to enforce security and compliance requirements, log normal or exception conditions and even handle transaction performance monitoring.


## __References__

1. https://www.ibm.com/docs/en/ibm-mq/8.0?topic=overview-introduction-message-queuing
2. https://stackify.com/message-queues-12-reasons/
3. https://www.g2.com/categories/message-queue-mq

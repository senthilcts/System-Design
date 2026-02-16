# System-Design
It has more about System design concepts
Server Server Server Horizontal Scaling Server  More CPU & RAM Vertical Scaling Server Server Server Server  More CPU & RAM    Hybrid Scaling Introduction:
When we deploy any service, there will be much user request. When we have limited users with 100 hit per second, the single
the server can handle the request and provide the response. Think if you have millions of users hitting one billion 
request per second, what will happen to the server? The server can't handle the request and system get failed.
Here we need change the configuration or increase of server. We may need to increase RAM, CPU, HDD, 
network speed etc.. This is called Scalability. The scalability is to able to handle the increasing load.

How to measure the scaling:


Request per second: How many API calls hits in the server

Number of consumers (Users): Number of users consume the API at the same time

Data Handling: The amount of Data handled in transit or rest

DB Query per sec: Number of DB queries process in a second

Messaging Rate: Number of messages process in a second

Vertical Scaling:
When a API called and if the response getting in considerable time then no issues. If the total response
time is taking more than half a second to process and send the response back is a big concern. Here we need
to think on scaling the system by increasing RAM, Memory, CPU or even network bandwidth. This is called
Vertical Scaling. 

 Server
4 CPU, 8GB RAM  Server
32 CPU, 256GB RAM Scales Up Pros:


No architectural change. Simply increase the capacity of the system

This will not change the system design and no extra work needed just increasing hardware

Cons:


Single point of failure: In case of any issue in the server, the entire system will not work

Hardware limitation: We can not scale the system as it has some limits

Downtime: When ever any maintenance related work, we may need to shutdown temporarily.

When to do Vertical Scaling:


Database performance issue: When DB face with high traffic and low response rate

Simple, monolithic application: We can do when we deal with legacy app like monolithic app

Resource intensive task: When a single node need more processing power.

For Startups: This can be useful for startup organizations where the number of users will be less

Horizontal Scaling:
When there are billions of request coming and each request process different database server in a 
microservice architecture, we need to increase the number of servers. This can be handled by load balancers.
This is called Horizontal scaling. Instead of increasing the power of one single server, you will increase 
number of servers. The load balancers will handle the request and this will distribute amoung the servers.


 Load balancer    Server 
1 Server 2 Server 3  Server 4  Server 5  Server n Pros:
High Availability / Fault tolerance: If one node fails, then other node will work for the request and it will
ensure no downtime
Increase I/O Concurrency: The DB read/write will be distributed across multiple machines
No limit: You can keep on increasing number of servers but it involves cost
Cost effective : when you increase the number of servers the cost will not increase compare with vertical 
scaling 

Cons:
Complexity of System: In distributed system, it is hard to troubleshoot, deploy and maintain
Data Consistency: In the horizontal scaling, maintaining synchronized data access server is challenging
Network overhead: Communication between servers added latency


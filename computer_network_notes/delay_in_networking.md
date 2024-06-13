# Delays in computer netwoking

We would like Internet services to be able to move as much as data we want between two systems, instantaneously, whithout any loss of data. But this is unachievable in reality.

There are several factors which affects the throughput (amount of data per second that can be tranferred) between 2 systems.

Both packet switching and circuit switching have delays in their respective networks. 

Packet switching has many points where delay can occur due to its dynamic nature.

while circuit switching gives a guranteed delivery and consistent transmission rate, they are also suseptible to delays.


## **Type of delays**

There are mainy 4 types of delay in a computer network 

**1. Transmission delay**

The time it takes for a packet to be completely transmitted from the source (host) to the transmission medium.

it is directly proportional to the packet size and inversly proportional to tranmission rate (bandwidth) of the link.

(Increasing the packet size will increase the tansmission delay. Increase the transmission rate (bandwidth) will decrease the transmission delay)

Transmission delay = packet size(L) / tranmission rate (B)

or 

Tt = L/B

L = packet size

B = bandwidth (transmission rate)


![tranmission_delay](https://media.geeksforgeeks.org/wp-content/uploads/20200322153702/picture218.png)

Factors affecting:

* packet size: larger packets take longer to tranmist due to more data bits needing to be sent
* Tranmission rate : the speed of the network medium (e.g., bandwidth) directly affects transmission time. Higher bandwidth leads to faster tranmission.


**2. Propagation delay**

The time taken by the last bit (data) of the packet to physically travel through the physical medium, (like cables or wireless channels) and reach the destination is known as propagation delay.

it is directly proportional to the distance and inversly proportional to propogation speed of the data in the medium.

(Increasing the distance will increase the propagation delay. Increaing the propagation speed will decrease the propagation delay)

propogation delay = distance / propagation speed

or

Tp = D/V

D = distance

V = velocity
    
    NOTE

    propagation speed (air) = 3 * 10^8 m/s.

    propagation speed (ofc) = 2.1 * 10^8 ms.
    

![propagation_delay](https://media.geeksforgeeks.org/wp-content/uploads/20200322154016/Picture37.png)

Factors affecting:

* distance: it take more time to reach the destination if the distance of the medium is longer.

* porpagation speed : if the propagation speed of the medium is higher, the packet will be recieved faster.


**3. Queuing delay**

This delay occurs when a packet arrive at a network device like a router or switch and has to wait in a queue in something called buffer, before being forwarded. So the amount of time it waits in a queue before being processed is called queuing delay. 

it significantly depends on the traffic load at a specific node.

Factors affecting:

* Network congestion: when multiple packets compete for limited resources on the network, queues form, causing delays.

* Limited processing power: If the network is overloaded or underpowered, it might take longer to process and forward packets, leading to quiuing delays.


**4. Processing delay**

The time it takes for a network device like router or switches to process a packet, including tasks like:

Header information check: Verifying the source and destination adderess, packet type etc.

Routing decisions: Determining the best path for forwarding the packet to its destination.

Updating internal tables: Maintaining routing information for efficient packet forwarding.

Factors affecting:

* Hadware capabilities: Processing power and efficiency of the network device can impact processing speed.

* Software complexity: Complex routing protocols or additional security checks might slighty increase processing time.

----------

Both queuing delay and processing delay doesn't have any formula because they depend on the speed of the processor.

The total network delay can be calculated as:

T total = Tt + Tp + Tq + Tpro

Ttotal = Tt + Tp

(when taking Tq and Tpro equal to 0)

T total = Total time
Tt = Transmission time
Tp = Propagation time
Tq = Queuing time
Tpro = Processing time

----------------
-----------------

## Impact of delays

These delays can accumulate as data travel through the netwok, impacting various aspects like:

* Latency: The time it takes for data to reach its destination, affecting response time in applicaitions like video conferencing and online gaming.

* Throughput: The amount of data transferred per second, impacting download/upload speeds and file transfers.

* Jitter: Variations in delay experienced by different packets, leading to disrupted audio/video quality in streaming applications.

### Minimizing delays:

Many different stratagies can be used to minimize the delays in a network, for example:

* Upgrading network infrastrucutres: Using higher bandwidth links (e.g., fiber optic) can reduce tranmission delay

* Optimizing routing protocols: Choosing efficient routing protocols can reduce processing delays and improve overall network performance.

* Implementing traffice shaping and prioritization: Managing network traffic and prioritizing critical applicaiton can minimize congestions and queuing delays.

* Enhancing processing power: Upgrading network devices with more powerful processors can improve their ability to handle data and reduce processing delay.

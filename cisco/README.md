# Cisco Packettrace, Cisco Packettracer or is it Cisco Packet Tracer :question:

<img src='../img/cisco.png' alt="banner"></img>


This is the real question all of them.

Answer to this question:
```
there is no wrong or right, we developer know exactly what we are talking about, right?
```

## What does it exactly :question:

CPT is an excellent piece of software for both experienced and inexperienced network administrators. It can do basically everything, like building the complete infrastructure of a firm and testing their network rules, for example, with a firewall or a switch. CPT is often used in schools to test their students in a specific area, such as port forwarding or blocking other things.


## Do I actually use it :sleeping:

To be honest, I never liked Cisco's PacketTracer because it still has the same user interface as it did ten years ago. And that's why I never used it on purpose. But as I grew older, I realized that I shouldn't focus solely on the outside. Now I still don't like it, but it has very nice tools to investigate network troubles. But, to be honest, it can quickly become **very** complicated and complex.

## Our exercises :school_satchel:
Here we will have some exercieses regarding CPT


<details>
<summary>Exercise 6 (Niveau 3 - Expert Skills :sunglasses:)</summary>
<br>
This was a very simple exercise which was about getting along with the CPT Command Line and some other sub-tasks.

-   Getting along with Command Line :white_check_mark:
-   Name all servers and routers with their IP address / CIDR :white_check_mark:
-   Fill out the routing table for all routers :white_check_mark:
-   Find out how the DHCP works in this scenario :white_check_mark:
</details>

<details>
<summary>Exercise 7 (Niveau 3 - Expert Skills :yum:)</summary>
<br>
This exercise was more difficult but still very doable to do. It was more of an process of elimination, fist go to the first notebook and try the ping. If this is not working try it on the second notebook and see the result. So forth and on.. 

I tried these short explained steps to figure out where the issue was located:

-   Ping on site from client, didn't worked - timeout
-   Ping the router, didn't also worked - timeout
-   Listen to trace to client, hops to the first router
-   Listen to trace from server to client, did work

After this I tried to look more into the routing between client and router and after a detailed look I saw there was an entry with an address which was pointing to a non existing address. 

The wrong route entry was deleted and then it worked!
</details>

<details>
<summary>Exercise 8 (Niveau 3 - Expert Skills :smiling_imp:)</summary>
<br>
This exercise was actually an easy one because the main focus was on dealing with dynamic routing.
First things first, this is the network we should build and use to get all the information from the network and every device. This practical exercise should teach us to plan and document all of the minor details of our network. Only in this manner are we fully aware of what is happening. 

<img src='../img/cisco_e8.png' alt="banner"></img>

## Purchasing Department PC11: 171.53.16.36 /28

| IP Address / Network                                        	| Number of Hostbits 	| Number of Hosts 	|
|-------------------------------------------------------------	|--------------------	|-----------------	|
| Address:    171.53.16.36 /28<br>Netmaks:    255.255.255.240 	|          4         	|        14       	|
|                                                             	|                    	|                 	|
| Network-ID: 171.53.16.32 /28                                	|                    	|                 	|
| 1st. IP:    171.53.16.33 /28                                	|                    	|                 	|
| Last IP:    171.53.16.46 /28                                	|                    	|                 	|
| Broadcast:  171.53.16.47 /28                                	|                    	|                 	|


## Purchasing Department PC12: 171.53.16.45 /28

| IP Address / Network                                        	| Number of Hostbits 	| Number of Hosts 	|
|-------------------------------------------------------------	|--------------------	|-----------------	|
| Address:    171.53.16.36 /28<br>Netmaks:    255.255.255.240 	|          4         	|        14       	|
|                                                             	|                    	|                 	|
| Network-ID: 171.53.16.32 /28                                	|                    	|                 	|
| 1st. IP:    171.53.16.33 /28                                	|                    	|                 	|
| Last IP:    171.53.16.46 /28                                	|                    	|                 	|
| Broadcast:  171.53.16.47 /28                                	|                    	|                 	|


## Logistics Department PC51: 113.25.0.68 /23

| IP Address / Network                                        	| Number of Hostbits 	| Number of Hosts 	|
|-------------------------------------------------------------	|--------------------	|-----------------	|
| Address:    113.25.0.68 /23<br>Netmaks:    255.255.255.240 	|          9         	|        510       	|
|                                                             	|                    	|                 	|
| Network-ID: 113.25.0.0 /23                                	|                    	|                 	|
| 1st. IP:    113.25.0.1 /23                                	|                    	|                 	|
| Last IP:    113.25.1.254 /23                                	|                    	|                 	|
| Broadcast:  113.25.1.255 /23                               	|                    	|                 	|


## Logistics Department PC52: 113.25.1.164 /23

| IP Address / Network                                        	| Number of Hostbits 	| Number of Hosts 	|
|-------------------------------------------------------------	|--------------------	|-----------------	|
| Address:    113.25.0.68 /23<br>Netmaks:    255.255.255.240 	|          9         	|        510       	|
|                                                             	|                    	|                 	|
| Network-ID: 113.25.0.0 /23                                	|                    	|                 	|
| 1st. IP:    113.25.0.1 /23                                	|                    	|                 	|
| Last IP:    113.25.1.254 /23                                	|                    	|                 	|
| Broadcast:  113.25.1.255 /23                               	|                    	|                 	|

</details>

<details>
<summary>Exercise 9 (Niveau 3 - Expert Skills :laughing:)</summary>
<br>
This exercise is similar to the previous one; the only difference is that we are dealing here with static routing. Same environment, same devices.

## Router0 I1 109.38.31.1 /30

| IP Address / Network                                        	| Number of Hostbits 	| Number of Hosts 	|
|-------------------------------------------------------------	|--------------------	|-----------------	|
| Address:    109.38.31.1 /30<br>Netmaks:    255.255.255.252 	|          2         	|        2       	|
|                                                             	|                    	|                 	|
| Network-ID: 109.38.31.0 /30                                	|                    	|                 	|
| 1st. IP:    109.38.31.1 /30                               	|                    	|                 	|
| Last IP:    109.38.31.2 /30                               	|                    	|                 	|
| Broadcast:  109.38.31.3 /30                              	    |                    	|                 	|


## Router1 I1 109.38.31.2 /30

| IP Address / Network                                        	| Number of Hostbits 	| Number of Hosts 	|
|-------------------------------------------------------------	|--------------------	|-----------------	|
| Address:    109.38.31.2 /30<br>Netmaks:    255.255.255.252 	|          2         	|        2       	|
|                                                             	|                    	|                 	|
| Network-ID: 109.38.31.0 /30                                	|                    	|                 	|
| 1st. IP:    109.38.31.1 /30                               	|                    	|                 	|
| Last IP:    109.38.31.2 /30                               	|                    	|                 	|
| Broadcast:  109.38.31.3 /30                              	    |                    	|                 	|



</details>
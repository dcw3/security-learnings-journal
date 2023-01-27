Jan 15
- Sorry haven't written in a while. I realized that my understanding of basic IT and networking is lacking, so I'm trying to brush up on this before getting more hands on. Trying to go through Daniel Miessler's recommendations for IT tasks to get comfortable with. With some Azure VM's I have gotten through the first few bullets: setting up an Active Directory forest with a corresponding DNS and DHCP server (though DHCP doesn't work in Azure since it's provided by the infrastructure).
- I was going to begin on "setting up multiple network zones" but I'm not sure what this entails and Googling didn't seem to help. If I had to do it right now I'd only know to manually configure Windows Firewall rules to do this. I think I probably need to understand this task better first.
- Right now I'm learning about routing basics. I learned some of this in undergrad but haven't used it and forgot some of it.
- Today I reviewed NAT and port forwarding and logged into my home router for the first time. So port forwarding seems similar to NAT in that both are passing traffic from external hosts to internal hosts through the router, and the router is translating the external traffic's destination (which is a port on the router) to the correct internal destination. However, a distinction is that NAT assignments are temporary and not publicly discoverable, whereas port forwarding is meant as a long-lived setting which enables a service running on an internal server to be publicly accessible.
- I also understood DHCP better after reading about how to set static IP's. In short it should be set from the DHCP server itself. In my Azure case that'll probably instead be through the web UI, though I think right now I'm setting it to request a certain IP from the DHCP server, on the network settings of the machine itself (have to double check).

Jan 18
- Spent some time watching Network+ videos on Udemy today. Some notable learnings include that port forwarding/mirroring is used on switches to duplicate traffic to enable surveillance and analysis, and VLAN's are relatively easy to set up and a very convenient and powerful way to segment your internal network. In fact, I think VLAN's is probably what the blog post meant when recommending setting up different network zones, but I will have to do some more learning before I'm sure of that.

Jan 19
- Spent some more time on Network+ videos, learned about Wifi standards. I didn't know that unidirectional antenna are used to help secure wireless networks by reducing the amount of external areas where the signal is reaching.

Jan 20
- I learned that if your ipconfig shows 169.254.x.x, that's an automatic IP address set by your device when DHCP fails. So DHCP failure can be diagnosed in this way.
- I also had no idea about IP multicast and broadcast.

Jan 21
- Learned about IPv6 addresses, I didn't know they were always 8 segments of 4 hexadecimal digits, and that :: means abbreviating zeros.
- Also learned that IPv6 uses Neighbor Discovery Protocol to discover hosts and routers on the local network, mitigating the need for the manual configuration of default gateway IP address on the machine.

Jan 25
- Been a busy few days. Watched some networking videos on the train. Got to review basic routing protocols such as BGP, and learned about interior networking protocols before promptly forgetting most of it, except that OSPF is the commonly used one.

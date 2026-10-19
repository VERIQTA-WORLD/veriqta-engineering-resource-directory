# Firewalls and VPNs

Start with the flow that should be allowed and the boundary that should reject another flow.

## Make the boundary explicit

| Open | What you can find | Access |
| --- | --- | --- |
| [Networking Fundamentals](https://www.practicalnetworking.net/index/networking-fundamentals-how-data-moves-through-the-internet/) | Follow the free introductory module on how data moves through networks. | Free module; further training separate |
| [Computer Networks: A Systems Approach](https://book.systemsapproach.org/) | Larry Peterson and Bruce Davie; connect protocols to the systems they support. | Free online textbook |
| [containerlab](https://containerlab.dev/) | Build reproducible network labs from topology definitions. | Free documentation and source; compatible host and images required |
| [Security Engineering](https://www.cl.cam.ac.uk/archive/rja14/book.html) | Ross Anderson; choose a security-design chapter to understand the assumptions around a control. | Author-hosted material; edition access varies |

## Focused references

**[WireGuard quick start →](https://www.wireguard.com/quickstart/)**  
Inspect the supported two-peer setup and key-handling instructions.  
**Free guide; own test endpoints required**

**[pfSense recipes →](https://docs.netgate.com/pfsense/en/latest/recipes/index.html)**  
Select a focused firewall or routing example with an explicit topology.  
**Free recipes; matching software and lab required**

## Follow the tools

[pfSense](../04-tools-and-technologies/pfsense.md) · [OPNsense](../04-tools-and-technologies/opnsense.md) · [WireGuard](../04-tools-and-technologies/wireguard.md) · [OpenVPN](../04-tools-and-technologies/openvpn.md)

## Put one idea to work

Record allowed and denied flows in an isolated lab and explain the relevant rule or route. Use the selected guide’s prerequisites and verification steps. Choose an owned or provided learning environment, keep sensitive data out of your notes, and remove the exercise resources when finished.

[Browse this collection](README.md) · [Directory homepage](../README.md)

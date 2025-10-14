#IoT #Semester4 #SRH
## VPC
Virtual private clouds (VPCs) are secure, individual and private cloud - computing models hosted within a public cloud. VPC networks are global and can have subnets in any cloud region worldwide.

VPCs are the networking foundation for most services and resources that can be deployed in the GCP. They are hosted remotely by a public cloud provider (like google cloud.)

### Key Features of VPCs:
- They connect to each other and to the internet
- Segmenting networks
- They can use firewall rules to restrict access instances
- They can define IP address spaces
- Can create subnets
- Can securely connect to on premises networks or other VPCs
#### Example of a segmented network using VPCs:
![[Pasted image 20251014161815.png]]

### Routing Tables:
- They are built in
- No router provisioning or managing 
- Forwarding traffic from on instance to another
- No external IP address required

### Firewall:
- Stateful by default (return traffic is automatically allowed, if you create a rule for outgoing requests.)
- Is a global resource.
- Restricts access to instances.
- No router provisioning or managing.
- Rules can be defined through network tags.
- Implicit deny for ingress by default.
- Rules are priority based.
- Logging can be enabled per rule.

### VPC Peering / Network Peering:
Allows the user to connect two separate VPC networks so that the resources in each network can communicate with each other using private, internal IP addresses.
If VPC A is peered with VPC B and VPC B is peered with VPC C, it does not mean that VPC A can communicate with VPC C through VPC B. Furthermore, two VPC networks that the user intends to peer cannot have overlapping subnet IP address (CIDR) ranges.
Lastly, firewall rules for each VPC are still in effect and therefore must be configured to allow the desired traffic from peered network's IP ranges.

### Network Topologies:
- Structure: All devices connect to a central point called a hub or switch. This central  device acts as a control point for all data traffic. 
- Centralized Control: The hub manages and directs all data communication. 
- Simplicity and Scalability: It's easy to add or remove devices without affecting the rest of the network.
- Single Point of Failure: If the central hub fails, the entire network goes down.
- High Cost: Can require more cabling than other topologies to connect each device individually to the central hub.
- Best for LANs and client-server architectures due to their reliability and their ease of management.

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
#### Linear:
- Structure: All devices connect to a central point called a hub or switch. This central  device acts as a control point for all data traffic. 
- Centralized Control: The hub manages and directs all data communication. 
- Simplicity and Scalability: It's easy to add or remove devices without affecting the rest of the network.
- Single Point of Failure: If the central hub fails, the entire network goes down.
- High Cost: Can require more cabling than other topologies to connect each device individually to the central hub.
- Best for LANs and client-server architectures due to their reliability and their ease of management.

#### Ring:
- Structure: Each device is connected to two other devices, forming a circular ring. Data  travels in a single direction (unidirectional) or both directions (bidirectional).
- No Central Point of Failure: Unlike a star topology, it doesn't rely on a central hub.
- High Reliability (With Dual Rings): A dual-ring setup provides redundancy, so if one link fails, data can still travel the other way.
- Vulnerability: A failure in a single device or cable segment in a single-ring topology can  disrupt the entire network.
- Difficult Troubleshooting:  It can be hard to pinpoint the location of a fault because of the circular data flow.
- Best For: Networks that require reliable performance and low-to-moderate traffic.

#### Mesh:
- Structure: Each device is directly connected to every other device in the network. This creates multiple redundant paths for data transmission. 
- Maximum Redundancy and Reliability: No single point of failure exists; if a path fails, data can be rerouted through another one. 
- High Cost and Complexity: Requires an extensive amount of cabling and complex setup due to the large number of connections.
- High Security: The decentralized structure makes it difficult for unauthorized access or data interception.
- Best For Mission-critical applications where network uptime is essential, such as in military or large-scale telecommunications networks.

## Load Balancing:
- Fully distributed, software-defined, managed service. 
- You can put Cloud Load Balancing in front of all of your traffic:  HTTP(S), TCP traffic, SSL traffic, UDP traffic .
- Provides single as well as cross-region load balancing, including  automatic multi-region failover.
- No “pre-warning” is required for anticipated spikes in traffic. 
- Examples: Application Load Balancer (HTTP(S)) - Layer 7; Network  Load Balancer (TCP/UDP/other IP protocols) - Layer 4 
### Example of Cloud Load Balancing:
![[Pasted image 20251014165614.png]]

## Locations and Regions
Regions are large and independent geographical areas that contain three or more distinct zones. Resources in a region share high speed network connectivity

Zones are single, isolated failure domains within a region. Zones protect applications from localized failures like power outages or fires in other zones.

Multi regions are geographic areas covering two or more  Regions (e.g., the EU or US multi regions) used primarily for  data storage and distribution.
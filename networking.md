# GCP-networking-notes

#### GCP Networking 
GCP has more then 70 points of presence across 33 countries creating the broadest reaching network of nay Cloud provider. 
All the google datacenters are connected their own private network.

###### Default/ legacy networking
- Networks are global resources
- Limited to 5 networks per project 
- Communication between networks uses external IPs
- Networks are the only mechanism to group VMs by IP address

######  Subnetworks
- Regional resources inside a global network resource
- 100 subnetworks per project
- Each subnetwork uses a single RFC 1918 CIDR range 
- Non-contiguous CIDR ranges
- communication between subnetworks can use internal IPs
- Firewalls and routes use instance tags

###### Subnetwork features
- Subnetworks partition your network into predictable IP address ranges
- Each subnetwork has a known CIDR range. All instances created in that subnetwork have internal IP addresses assigned from a CIDR range
- Subnetwork ranges can be automatically allocated (auto subnet network) or specifically chosen by you (custom subnet network).
- Each subnetwork is restricted to a single region, but you can chooose to confine instances to a zone if you desire ...

###### Auto subnet IP ranges 

| Region       | IP range      |
| -----------  | --------------|
| us-central1  | 10.128.0.0/20 |
| us-east1     | 10.142.0.0/20 |
| europe-west1 | 10.132.0.0/20 |
| asia-east1   | 10.140.0.0/20 |

###### Manual subnet IP ranges
- Manually created subnetworks,can use any valid RFC1918 IP range
- Ranges do not have to be contiguous between networks

###### Subnetwork isolation
- Tag all instances in subnet-a, subnet-b, and subnet-c
- create the firewall rules using **--target-tags** to enable communication between subnet-a and subnet-b and between subnet-a and subnet-c

##### Connecting to Google Cloud
###### Cloud VPN
###### Cloud BGP Router

#### Network Services
###### Load Balancer


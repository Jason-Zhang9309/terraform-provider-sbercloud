## Example: ECS Instance of s6 flavor, with EIP

### Requirements

- key pair exists in SberCloud.Advanced
- subnet exists in SberCloud.Advanced

### Description

This example provisions an ECS instance with the following attributes:
- availability zone: AZ1 ("ru-moscow-1a")
- flavor: s6.large.4
- OS: Ubuntu 20.04
- 1 security group: "default"
- one system EVS disk of "High I/O" type (SAS) and 16 GB size. 

Then EIP is created and associated with the ECS:
- EIP bandwidth: 4 Mbit/s
- Bandwidth charging type: by traffic.  

### Notes

Please note how the list of availability zones is obtained.

Please note the **sbercloud_compute_flavors** data source.  
It gets the right flavor name based on the performance type, vCPU and RAM amount required.  
The following performance types are available:
- "normal": General-purpose
- "computingv3": Dedicated general-purpose
- "highmem": Memory-optimized
- "diskintensive": Disk-intensive
- "gpu": GPU-accelerated


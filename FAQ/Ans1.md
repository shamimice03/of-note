### IP Address
- A Ip address is an identifier for a computer or device on a network
- IP address consists of two parts
   - Network address and Host Address

### Subnet Mask
- A subnet mask reveals how many bits in the IP address are used for network by masking the network portion of the IP address.
  <img width="1287" alt="Screenshot 2023-07-11 at 23 43 06" src="https://github.com/shamimice03/of-note/assets/19708705/f59c6bc5-d95f-4ad3-a849-747eae1aa237">
  <img width="1285" alt="Screenshot 2023-07-11 at 23 44 26" src="https://github.com/shamimice03/of-note/assets/19708705/e457b995-1b35-4953-931e-a459ef681ab1">
  <img width="1278" alt="Screenshot 2023-07-11 at 23 45 08" src="https://github.com/shamimice03/of-note/assets/19708705/71c7bf24-6ecd-40fc-8c25-d6be3ef89dbc">

### Why does an IP address have a network and a host part?
-  The reason for this is manageability. It's for breaking down a large network into smaller networks or sub-networks. Which is known as subnetting.
-  Ip addresses have a network and host portion, so that network can be logically broken down into smaller networks, which is known as subnetting.

### Subnetting
- Subnetting is done by changing the default subnet mask by borrowing some of the bits from the host portion.
Suppose, Let's say we have a subnet (255.255.255.0), which will able to create 1 network with 256 hosts. But technically we can have only 254 hosts. Because first
and the last IP addresses are reserved for network and broadcasts respectively.
  <img width="1265" alt="Screenshot 2023-07-12 at 0 00 29" src="https://github.com/shamimice03/of-note/assets/19708705/d073372e-7451-43b3-a78a-e11c844940d0">
  <img width="1273" alt="Screenshot 2023-07-12 at 0 00 52" src="https://github.com/shamimice03/of-note/assets/19708705/d0365fd5-0709-4a77-805d-255bfcd6df24">
  <img width="1277" alt="Screenshot 2023-07-12 at 0 01 06" src="https://github.com/shamimice03/of-note/assets/19708705/7ddd3229-b810-47b8-832e-f52d4affc61c">
  <img width="1268" alt="Screenshot 2023-07-12 at 0 01 20" src="https://github.com/shamimice03/of-note/assets/19708705/5c16879e-7329-4423-9df9-1b9d90986599">
  <img width="1277" alt="Screenshot 2023-07-12 at 0 01 58" src="https://github.com/shamimice03/of-note/assets/19708705/1b3a17a5-1193-4811-9182-b4f82a3e5dfc">
  <img width="1271" alt="Screenshot 2023-07-12 at 0 03 58" src="https://github.com/shamimice03/of-note/assets/19708705/e5086113-0030-4a90-a9c1-c93e6e3e7368">
  <img width="1270" alt="Screenshot 2023-07-12 at 0 04 29" src="https://github.com/shamimice03/of-note/assets/19708705/e3d5736d-cd6f-4f8f-a749-689d0dc007d7">
  <img width="1280" alt="Screenshot 2023-07-12 at 0 04 39" src="https://github.com/shamimice03/of-note/assets/19708705/38e43c95-3e45-4797-9aeb-905defbe5b61">

### CIDR 
Classless Inter-Domain Routing (Slash Notation)
- Subnet mask can be represented using the slash notation.
- Example:  `10.3.97.5/24`  - Here subnet mask is ( 255.255.255.0)
<img width="1276" alt="Screenshot 2023-07-12 at 0 06 16" src="https://github.com/shamimice03/of-note/assets/19708705/57d9e86e-5936-4946-918e-cc25ddce304f">

#### Refs: 
- https://www.youtube.com/watch?v=s_Ntt6eTn94&ab_channel=PowerCertAnimatedVideos

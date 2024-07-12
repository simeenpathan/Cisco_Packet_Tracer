# Cisco_Packet_Tracer

Sure! Below is a sample README file for your project on GitHub.

---

# College Campus Network Security Project

## Project Overview

This project focuses on enhancing the security of a college campus network by implementing web content filtering using Access Control Lists (ACLs) in Cisco Packet Tracer. The primary goal is to restrict access to specific categories of websites and ensure that network resources are used appropriately by students and faculty.

## Problem Statement 3: Restrict Access to Irrelevant Sites

### Problem Scenario

The college has discovered that students are misusing campus resources by accessing irrelevant sites. They require a solution to restrict access to only allowed categories of web content.

### Tasks & Submission

1. **Explore Options:**
   - Investigate how to achieve web content filtering and what network security products can provide this capability.
   
2. **Update Network Topology:**
   - Incorporate the necessary components into the existing campus network topology to support web content filtering.

3. **Explain Reasoning:**
   - Detail the rationale behind the chosen solution, including the risks and advantages.

4. **Write Policies:**
   - Develop and document the policies that will be applied to control web content access.

## Solution

### Implementation Steps

1. **Network Topology Update:**
   - Added a DNS server to the network to manage domain-based filtering.
   - Configured routers and switches to support ACL-based filtering.

2. **Define Access Control Lists (ACLs):**
   - Created extended ACLs to permit general web traffic (HTTP/HTTPS) and block access to specific domains.

### ACL Configuration

```plaintext
ip access-list extended WEB_FILTER
  permit tcp any any eq 80
  permit tcp any any eq 443
  deny tcp any any eq 80 www.facebook.com
  deny tcp any any eq 443 www.facebook.com
  deny tcp any any eq 80 www.instagram.com
  deny tcp any any eq 443 www.instagram.com
  permit ip any any
```

- **Explanation:**
  - `permit tcp any any eq 80`: Allows HTTP traffic.
  - `permit tcp any any eq 443`: Allows HTTPS traffic.
  - `deny tcp any any eq 80 www.facebook.com`: Blocks HTTP traffic to Facebook.
  - `deny tcp any any eq 443 www.facebook.com`: Blocks HTTPS traffic to Facebook.
  - `deny tcp any any eq 80 www.instagram.com`: Blocks HTTP traffic to Instagram.
  - `deny tcp any any eq 443 www.instagram.com`: Blocks HTTPS traffic to Instagram.
  - `permit ip any any`: Permits all other IP traffic.

### Verification

- Ensured that the ACLs were applied correctly by testing network access to restricted and permitted sites.
- Verified the configuration using `show running-config` command.

## Reasoning Behind the Solution

### Advantages

- **Enhanced Security:** Restricts access to non-educational websites, reducing potential misuse.
- **Bandwidth Optimization:** Ensures that network bandwidth is used for academic purposes.
- **Policy Compliance:** Enforces college policies regarding acceptable use of network resources.

### Risks

- **Overblocking:** May inadvertently block legitimate educational resources if not properly managed.
- **Complexity:** Requires ongoing monitoring and updates to maintain effectiveness.
- **User Frustration:** Users may be frustrated if legitimate sites are blocked or if policies are too restrictive.

## Conclusion

By implementing these ACL-based policies, the college can effectively manage and secure its network, ensuring that resources are used appropriately while minimizing the risk of misuse. Regular review and adjustment of ACLs are necessary to adapt to changing requirements and threats.

## Files Included

- `CampusNetworkSecurity.pkt`: Cisco Packet Tracer file containing the network topology and configuration.
- `README.md`: This documentation file.

## How to Run

1. Open Cisco Packet Tracer.
2. Load the `CampusNetworkSecurity.pkt` file.
3. Review the network topology and configuration.
4. Test the ACLs by attempting to access restricted and permitted websites from simulated devices.


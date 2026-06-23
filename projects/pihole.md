# Pi-hole Deployment Project

## Objective

* Deploy Pi-hole on Raspberry Pi
* Implement network-wide ad blocking
* Learn DNS and DHCP concepts
* Configure Raspberry Pi as DHCP server

## Environment

Hostname: CyberVoid
Pi-hole IP: 192.168.1.133
Gateway: 192.168.1.254
Router: AT&T Gateway

## Problem Encountered

After installation:

* Dashboard showed 0 queries
* No clients appeared
* DNS filtering was inactive

## Troubleshooting Process

### Step 1: Verify Pi-hole DNS

Command:

nslookup google.com 192.168.1.133


Result:

Pi-hole successfully resolved DNS requests.

Conclusion:

Pi-hole was functioning correctly.

### Step 2: Identify Active DNS Servers

Command:

ipconfig /all

Observed:

192.168.1.254
2600:1702:8157:9120::1

Conclusion:

Clients were using AT&T DNS instead of Pi-hole.

### Step 3: Manual DNS Testing

Configured laptop DNS manually:

192.168.1.133

Result:

Queries immediately appeared in Pi-hole.

Conclusion:

Pi-hole functionality confirmed.

### Step 4: DHCP Investigation

Discovered:

AT&T gateway does not allow custom DNS distribution through DHCP.

Solution:

Disable AT&T DHCP
Enable Pi-hole DHCP

## Final Configuration

### AT&T Gateway

DHCP: Disabled

### Pi-hole

DHCP: Enabled

Range:
192.168.1.64 - 192.168.1.253

Gateway:
192.168.1.254

## Results

Total Queries: 129
Queries Blocked: 15
Blocked Percentage: 11.6%
Active Clients: 4

### Verified

* DNS resolution functioning
* DHCP lease distribution functioning
* Multiple devices connected
* Advertisement blocking operational

## Lessons Learned

### DNS

Translates hostnames into IP addresses.

### DHCP

Distributes IP addresses, gateway information, and DNS settings.

### Static IP Addressing

Required to ensure clients can consistently locate Pi-hole.

### Troubleshooting Methodology

The root cause was not Pi-hole itself.

The issue was that the router continued advertising AT&T DNS servers through DHCP, preventing client devices from using Pi-hole automatically.

## Project Outcome

SUCCESSFUL

Pi-hole now operates as both:

* DNS Server
* DHCP Server

for the local network.

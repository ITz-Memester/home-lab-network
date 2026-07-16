# pfSense Firewall Configuration

## What I Did

Installed and configured pfSense as the network router and firewall for the home lab.
<img width="715" height="398" alt="image" src="https://github.com/user-attachments/assets/be5e0a4f-16eb-4679-87f3-eee65484c066" />

### Initial Setup
- Installed pfSense Plus 2.8.1 on VirtualBox
- Assigned interfaces: em0 (WAN/NAT), em1 (LAN/vboxnet0)
- Set LAN IP to 192.168.10.1/24
- Configured DHCP to serve IPs from 192.168.10.100 to 192.168.10.200
- Changed admin password from default

### Key Configuration
- Hostname: pfSense
- Domain: corp.local
- DNS Resolver: Enabled (forwards external queries to 8.8.8.8)
- DHCP Server: Active on LAN interface

## Why This Matters

pfSense is the **gateway** of the entire lab network. It:
1. Routes traffic between your lab VMs and the internet (via NAT)
2. Hands out IP addresses automatically (DHCP)
3. Answers DNS lookups (DNS Resolver)
4. Enforces firewall rules (will add rules later)

Without pfSense, your VMs can't talk to each other or reach the internet.

## Verification

- ✓ Ubuntu VM got IP 192.168.10.100 via DHCP
- ✓ `ping 8.8.8.8` works from Ubuntu (internet connectivity confirmed)
- ✓ pfSense web dashboard accessible at http://192.168.10.1
- ✓ DNS Resolver active and forwarding queries

## Next Steps

- Add DHCP static mapping for Windows Server DC once it's built (192.168.10.10)
- Create firewall rules to test with Kali later


# Day 3 — Networking Fundamentals & Troubleshooting (09/28/2026)

## Environment

* Virtual Machine: LCS-DC01
* Operating System: Windows Server 2025 Standard Evaluation (Desktop Experience)
* Hypervisor: VirtualBox
* Network Mode: NAT

## Objectives

* Understand basic IPv4 network configuration
* Identify the purpose of subnet masks, default gateways, DHCP, and DNS
* Practice common Windows networking commands
* Understand the difference between network connectivity and DNS resolution
* Troubleshoot DHCP and DNS issues
* Apply a structured troubleshooting methodology to a simulated Help Desk ticket

## Network Configuration

Initial network configuration observed on LCS-DC01:

* IPv4 Address: `10.0.2.15`
* Subnet Mask: `255.255.255.0`
* Default Gateway: `10.0.2.2`
* DHCP Enabled: Yes
* DHCP Server: `10.0.2.2`
* DNS Server: `192.168.1.1`

The VM is currently using VirtualBox NAT networking. The VirtualBox NAT gateway and DHCP server are both using `10.0.2.2`.

## Networking Commands Practiced

### `ipconfig`

Used to view the VM's IPv4 address, subnet mask, and default gateway.

### `ipconfig /all`

Used to examine additional network configuration information, including:

* DHCP status
* DHCP server
* DNS servers
* Network configuration details

### `ping`

Used to test connectivity at different points in the network.

Tests performed successfully:

* `ping 127.0.0.1`
* `ping 10.0.2.15`
* `ping 10.0.2.2`
* `ping 8.8.8.8`
* `ping google.com`

These tests demonstrated successful communication with the local TCP/IP stack, the VM's network interface, the default gateway, an external IP address, and a hostname requiring DNS resolution.

### `tracert`

Used `tracert google.com` to examine the path traffic takes between the VM and an external destination.

The first hop corresponded to the VirtualBox gateway (`10.0.2.2`). Additional hops represented routers farther along the path to the destination.

### `nslookup`

Used `nslookup google.com` to investigate DNS resolution.

The configured DNS server successfully returned multiple IPv4 and IPv6 addresses for Google.

Also tested:

`nslookup google.com 8.8.8.8`

This demonstrated that a specific DNS server can be queried directly and that different DNS servers may return different addresses for the same domain.

## DHCP Troubleshooting Exercise

A DHCP failure scenario was intentionally created using:

```cmd
ipconfig /release
```

After releasing the DHCP lease, the VM received an automatic private IP address in the `169.254.x.x` range.

This demonstrated APIPA (Automatic Private IP Addressing), which can occur when Windows cannot obtain a valid IPv4 address from DHCP.

The DHCP configuration was restored using:

```cmd
ipconfig /renew
```

The VM received its original address again:

`10.0.2.15`

Connectivity was then verified with:

```cmd
ping 10.0.2.2
ping google.com
```

Both tests succeeded.

### Troubleshooting Lesson

A `169.254.x.x` address can be an important indication that a computer was unable to obtain a valid DHCP configuration.

## DNS Troubleshooting Exercise

A nonexistent domain was queried using:

```cmd
nslookup nonexistentdomain12345.com
```

The DNS server returned an indication that the domain did not exist (NXDOMAIN).

This demonstrated that a DNS server can be functioning correctly while returning a negative response for a domain that does not exist.

## Simulated Help Desk Ticket — DNS Failure

### Ticket #006

**User:** Alex

**Issue:** User reported that the computer appeared to be connected to the network but could not access any websites.

### Troubleshooting Performed

1. Tested `google.com` with `ping`.

   * Hostname could not be resolved.

2. Tested external connectivity using:

   ```cmd
   ping 8.8.8.8
   ```

   * Successful with 0% packet loss.

3. Tested DNS resolution:

   ```cmd
   nslookup google.com
   ```

   * DNS request timed out.

4. Tested Google DNS directly:

   ```cmd
   nslookup google.com 8.8.8.8
   ```

   * Successfully returned Google's IP addresses.

### Diagnosis

The available evidence indicated that Internet connectivity was functioning, while the computer's configured DNS server was not successfully resolving DNS queries.

This differentiated a DNS resolution problem from a general Internet connectivity problem.

### Troubleshooting Lesson

A structured troubleshooting process can isolate the layer where a network problem occurs:

**Local system → network interface → gateway → Internet connectivity → DNS resolution**

## Key Concepts Learned

* IPv4 addresses identify devices on a network.
* Subnet masks define the local network/subnet.
* Default gateways provide a path to other networks.
* DHCP automatically provides network configuration to clients.
* DNS translates hostnames into IP addresses.
* APIPA addresses (`169.254.x.x`) can indicate a DHCP configuration problem.
* `ping` can test connectivity but does not diagnose every networking problem.
* `nslookup` is useful for investigating DNS resolution.
* Different DNS servers can return different IP addresses for the same hostname.
* A computer can have working Internet connectivity while DNS resolution is failing.
* Troubleshooting should proceed from evidence rather than assumptions.

## Troubleshooting Methodology

The Day 3 exercises reinforced the following troubleshooting model:

**Symptom → Gather Evidence → Form Hypothesis → Test → Identify Cause → Correct → Verify**

## Status

**Day 3: COMPLETE**

Completed:

* [x] IPv4 fundamentals
* [x] Subnet masks
* [x] Default gateways
* [x] DHCP fundamentals
* [x] DNS fundamentals
* [x] `ipconfig`
* [x] `ping`
* [x] `tracert`
* [x] `nslookup`
* [x] DHCP release/renew exercise
* [x] APIPA troubleshooting
* [x] DNS troubleshooting
* [x] Simulated networking Help Desk ticket

## Next Steps

Day 4 will focus on Windows command-line fundamentals and additional troubleshooting commands, including:

* `hostname`
* `whoami`
* `systeminfo`
* `tasklist`
* `taskkill`
* Additional command-line troubleshooting techniques

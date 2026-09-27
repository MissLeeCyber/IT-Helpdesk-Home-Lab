# Ticket 003 – Wi-Fi Not Working (09/25/2026)

## User Report

**User:** Jessica
**Issue:** Wi-Fi is not working.

Jessica reports that she is unable to connect to the company's wireless network.

## Initial Assessment

The first step is to determine the scope of the issue.

Ask whether other employees are also unable to connect to the wireless network.

* **One user affected:** Investigate the user's computer, wireless adapter, configuration, or credentials.
* **Multiple users affected:** Investigate the wireless network, access point, DHCP, router, or broader network outage.

## Troubleshooting Steps

### 1. Determine the Scope

Asked whether other employees were experiencing the same issue.

This helps determine whether the problem is likely isolated to Jessica's computer or affecting multiple users.

### 2. Check Wi-Fi Settings

On the user's computer:

* Verified that Wi-Fi is enabled.
* Confirmed that Airplane Mode is disabled.
* Checked whether the company's wireless network/SSID was visible.
* Attempted to reconnect to the appropriate wireless network.

### 3. Check the Wireless Adapter

Opened Device Manager and checked the network adapter for:

* Warning indicators
* Driver problems
* Disabled hardware
* Device errors

If a driver or device issue was identified, the appropriate troubleshooting procedure would be followed.

### 4. Check IP Configuration

Opened Command Prompt and ran:

```text
ipconfig
```

Reviewed the network adapter information, including:

* IPv4 address
* Subnet mask
* Default gateway

An invalid or missing IP configuration could indicate a DHCP or connectivity problem.

### 5. Test Network Connectivity

Used connectivity tests to determine where communication was failing.

Potential tests include:

```text
ping 127.0.0.1
ping <default-gateway>
ping 8.8.8.8
```

These tests can help determine whether the problem is with the local TCP/IP stack, the local network/gateway, or connectivity beyond the local network.

### 6. Test DNS Resolution

If internet connectivity by IP address works but websites cannot be reached by name, DNS may be the cause.

Used:

```text
nslookup google.com
```

to test DNS name resolution.

### 7. Verify the Resolution

After making the appropriate change:

* Reconnected to the wireless network.
* Confirmed the computer received a valid IP configuration.
* Tested connectivity.
* Confirmed that the user could access the required network resources.

## Troubleshooting Method

**Scope → Wi-Fi Settings → Adapter → IP Configuration → Gateway → Internet → DNS → Verification**

## Resolution

The exact cause and resolution would depend on the evidence discovered during troubleshooting.

## Skills Demonstrated

* Wireless troubleshooting
* Network troubleshooting
* Device Manager
* Command Prompt
* `ipconfig`
* `ping`
* `nslookup`
* DHCP fundamentals
* DNS fundamentals
* Troubleshooting scope

## Key Takeaway

Determining the scope of a problem is an important first step in network troubleshooting. A problem affecting one computer may require endpoint troubleshooting, while a problem affecting many users may indicate a network or infrastructure issue.

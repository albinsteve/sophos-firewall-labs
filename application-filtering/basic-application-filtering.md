# Basic Application Filtering Lab

## Objective
Block selected applications using Sophos Application Filter.

## Lab Environment
- Sophos Firewall Home Edition
- LAN: 192.168.1.0/24
- WAN: DHCP Internet

## Configuration Steps

### Step 1 - Create Application Filter Policy

Navigate to:

```text
Protect > Application Filter
```

Created a policy to block:
- Streaming Media
- Peer-to-Peer
- Remote Access Applications

### Step 2 - Apply Policy

Applied the application filter policy to the LAN to WAN firewall rule.

### Step 3 - Test
## Application Filter Verification

Tested applications:
- YouTube → Blocked
- TeamViewer → Blocked

Tested BitTorrent traffic after applying the application filter policy.

### Observed Behavior

The torrent client opened successfully but remained stuck at:

```text
Connecting to peers
```
Observed:
- 0 KB download
- No peer connections established
- No tracker communication

### Analysis

Sophos Application Filter successfully identified and blocked BitTorrent traffic using Layer 7 application signatures.

This demonstrated that application filtering works independently of traditional port-based filtering.

## Key Learning

- Application filtering operates at Layer 7
- DPI engine identifies application signatures
- Application filtering differs from web filtering
- SSL inspection improves application visibility

 ## Key Observation

Application filtering identifies traffic using application signatures instead of only URLs or ports.

## Web Filtering vs Application Filtering

| Web Filtering | Application Filtering |
|---|---|
| Controls websites | Controls applications |
| Uses URL/category database | Uses DPI signatures |
| Example: facebook.com | Example: Facebook App |
| Domain-based | Traffic behavior-based |

This allows the firewall to detect and block applications such as BitTorrent even when:
- Non-standard ports are used
- Encrypted traffic is used


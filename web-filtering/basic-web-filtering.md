# Basic Web Filtering Lab

## Objective
Block social media websites for LAN users.

## Lab Environment
- Sophos Firewall Home Edition
- LAN Network: 192.168.1.0/24
- WAN: DHCP Internet

## Configuration Steps

### Step 1 - Create Web Policy
Navigate to:

```Protect>
Web > Policies
```

Created a policy to block:
- Social Networking
- Streaming Media

### Step 2 - Apply Policy
Applied the web policy to the LAN to WAN firewall rule.

### Step 3 - Test
Tested from client PC:
- Facebook → Working
- YouTube → Working

### Problem
HTTPS websites were still accessible even after applying the web filtering policy.

### Root Cause
Encrypted HTTPS traffic could not be inspected by the firewall.

### Fix
Enabled HTTPS Decryption and Inspection on the firewall.

### Test
Tested from client PC:
- Facebook → Blocked
- YouTube → Blocked

### Result
Blocked HTTPS websites were filtered successfully.


## Troubleshooting

### Problem
Websites were still accessible.

### Root Cause
Web policy was not attached to firewall rule.

### Fix
Attached web policy correctly.

## Key Learning
- Web filtering works through firewall rules
- HTTPS inspection may be required
- Policy order is important

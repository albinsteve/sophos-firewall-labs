## SSL Certificate Trust Issue

After enabling HTTPS decryption, browsers displayed certificate warnings.

### Initial Issue
The wrong CA certificate was installed on the client device.

Installed certificate:
```text
Default_CA
```

However, the firewall was using a different certificate for HTTPS inspection:
```text
Sophos SSL CA
```

### Resolution
Downloaded the correct SSL inspection certificate from:

```text
Web > General Settings
```

Installed the certificate into:
```text
Trusted Root Certification Authorities
```

### Result
HTTPS inspection worked successfully without browser certificate warnings.

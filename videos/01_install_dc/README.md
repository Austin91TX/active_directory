# 01 Installing the Domain Controller

1. Use 'sconfig' to:
    - Change the hostname
    - CHange the IP address to static
    - Change the DNS server to our own IP address

2. Install the Active Directory Windows Feature

```shell
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
```

```
import-Module ADDSDeployment
```

```
Install-ADDSForest
```

DomainName: xyz.com

# restart DC1

Get-NetIPAddress
Get-NetIPAddress 192.168.11.155

Get-DNSClientServerAddress
# find InterfaceIndex
Set-DNSClientServerAddress -InterfaceIndex x -ServerAddresses 192.168.11.155

#
# on WS01
```
Add-Computer -DomainName xyz.com -Credential xyz/Administrator -Force -Restart
```
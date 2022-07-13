#Active Directory Setup

#01 installing the Donmain Controller
1. Use 'sconfig'
    - Change the hostname
    - change the IP address to static
    - Change the DNS server to our own IP address

2. Install the Active Directory Windows Feature
```shell
Install-WindowsFeature AD-Domain-Services - IncludeManagementTools
```
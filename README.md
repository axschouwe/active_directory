#Active Directory Setup

#01 installing the Donmain Controller
1. Use 'sconfig'
    - Change the hostname
    - change the IP address to static
    - Change the DNS server to our own IP address

2. Install the Active Directory Windows Feature
```shell
Install-WindowsFeature AD-Domain-Services - IncludeManagementTools
Import-Module ADDSDeployment
Install-ADDSForest
```
    - powershell cmdlets
    -set static ip
    Get-NetIPAddress -IPAddress '192.168.100.156'

    -set trusted host
    set-item wsman:\localhost\client\trustedhosts -value 192.168.26.24

    -Enter a powershell session
    Enter-PSSession 192.168.26.24 -Credential (Get-Credential)

    -Get DNS client
    Get-DNSClientServerAddress

    -Set DNS Client server address to DC ip
     Set-DNSClientServerAddress -InterfaceIndex 9  -ServerAddress 192.168.26.24

     -Shutdown
      shutdown /s /t 0

      
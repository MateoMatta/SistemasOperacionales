1.
Comando
```
PS C:\Users\MateoML> Get-Process | Select-Object Name, ID, Responding | Format-Table -AutoSize
```

Resultado
Name                   Id Responding
----                   -- ----------
AcroRd32             6388       True
AcroRd32             9208       True
AESTSr64             2032       True
armsvc               1972       True
audiodg              4392       True
BleServicesCtrl      2340       True
conhost              2660       True
csrss                 440       True
csrss                 572       True
devmonsrv            5116       True
dwm                  1808       True
eclipse              6124       True
EpicGamesLauncher    2764       True
esrv_svc             5836       True
explorer             1964       True
GoogleCrashHandler   2400       True
msedge               7800       True
msedge               7900       True
msedge               8120       True
msedge               8616       True
msedge               9628       True
msedge               9708       True
nusb3mon              560       True
nvcontainer          1704       True
nvcontainer          2596       True
NVDisplay.Container   848       True
NVDisplay.Container  1240       True
NVIDIA Web Helper    2580       True
NvTelemetryContainer 2148       True
obexsrv              4348       True
OfficeClickToRun     1136       True
ONENOTE              5652       True
ONENOTEM              888       True
svchost               136       True
svchost               452       True
svchost               788       True
svchost               904       True
svchost               992       True
svchost              1112       True
svchost              1336       True
svchost              1756       True
svchost              2236       True
svchost              2288       True
svchost              3748       True
svchost              4108       True
svchost              5712       True
System                  4       True
taskeng              8220       True
taskhost             1828       True
taskhost             6952       True
UnrealCEFSubProcess   900       True
UnrealCEFSubProcess  4456       True
urbanvpnserv         3256       True
wininit               552       True
winlogon              644       True
wisptis              3308       True
WmiPrvSE             4876       True
WmiPrvSE             6980       True
WUDFHost             4204       True
XBoxStat             2328       True

2. 
Comando
```
PS C:\Users\MateoML> Get-Process | Format-Table Name, Id, @{Name='VM (MB)';Expression={$_.VM / 1MB -as [int]}}, @{Name='PM (MB)'; Expression={$_.PM / 1MB -as [int]}}
```
Resultado
Name                   Id VM (MB) PM (MB)
----                   -- ------- -------
AcroRd32             6388     417     180
AcroRd32             9208     121      12
AESTSr64             2032      15       2
armsvc               1972      40       1
audiodg              4392      98      30
BleServicesCtrl      2340      89       4
conhost              2660      47       2
csrss                 440      48       3
csrss                 572     165       4
devmonsrv            5116      72       5
dwm                  1808     199      43
eclipse              6124    3057     709
EpicGamesLauncher    2764     805     220
esrv_svc             5836     185      65
explorer             1964     416      73
GoogleCrashHandler   2400      45       2
GoogleCrashHandler64 2496      42       2
hkcmd                2752      69       4
Idle                    0       0       0
igfxpers             2800      79       5
InputMapper          2484     776      94
javaw                6872    3670     212
jucheck              7136     103       5
jusched               508      84       3
lsass                 656      48       8
lsm                   664      23       3
mediasrv             4400      74       9
msedge                480    4896     244
msedge               1224    4565      51
msedge               1316    4487      30
msedge               1588    4537      57
msedge               2096     126       4
msedge               4072    1225     137
msedge               5592     344      15
msedge               6372    4409      26
msedge               6488    4606      75
msedge               7180      86       4
msedge               7288     881     211
msedge               7296     464      50
msedge               7712    8709      79
msedge               7800    4474      28
msedge               7900    4549      54
msedge               8120    4477      41
msedge               8616    8761     157
msedge               9628    4528      50
msedge               9708    4444      23
nusb3mon              560      83       3
nvcontainer          1704     136      12
nvcontainer          2596     218      46
NVDisplay.Container   848      67       5
NVDisplay.Container  1240     198      29
NVIDIA Web Helper    2580     285      29
NvTelemetryContainer 2148      78       7
obexsrv              4348      59       3
OfficeClickToRun     1136     183      34
ONENOTE              5652     580     111
ONENOTEM              888      74       42
System                  4       3       0
taskeng              8220      32       3
taskhost             1828      82       9
taskhost             6952      79       5
UnrealCEFSubProcess   900     418      69
UnrealCEFSubProcess  4456    1077      93
urbanvpnserv         3256     114      24
wininit               552      48       3
winlogon              644      58       4
wisptis              3308      63       4
WmiPrvSE             4876      76      14
WUDFHost             4204      43       3
XBoxStat             2328      84       5

3.   
Comando  
```
PS C:\Users\MateoML> Get-EventLog -List | Format-Table @{Name='LogName';Expression={$_.LogDisplayName}}, @{Name='Periodo de Retencion';Expression={$_.minimumRetentionDays}}
```
Resultado
LogName                                               Periodo de Retencion
-------                                               --------------------
Aplicación                                                               0
Dell                                                                     7
ESRV_SVC_QUEENCREEK                                                      7
Eventos de hardware                                                      0
Internet Explorer                                                        7
Key Management Service                                                   0
Media Center                                                             0
Microsoft-Windows-Diagnostics-Performance/Operational                    7
Microsoft Office Alerts                                                  0
                                                                          
Sistema                                                                  0
USER_ESRV_SVC_QUEENCREEK                                                 7
Windows PowerShell                                                       0

4.
Comando
 ```   
PS C:\Users\MateoML> Get-Service | Sort-by Status | Format-List -GroupBy status
```

Resultado

 Status: Stopped


Name                : OpenVPNServiceLegacy
DisplayName         : OpenVPN Legacy Service
Status              : Stopped
DependentServices   : {}
ServicesDependedOn  : {tap0901, Dhcp}
CanPauseAndContinue : False
CanShutdown         : False
CanStop             : False
ServiceType         : Win32ShareProcess

Name                : SensrSvc
DisplayName         : Brillo adaptable
Status              : Stopped
DependentServices   : {}
ServicesDependedOn  : {}
CanPauseAndContinue : False
CanShutdown         : False
CanStop             : False
ServiceType         : Win32ShareProcess

Name                : seclogon
DisplayName         : Inicio de sesión secundario
Status              : Stopped
DependentServices   : {}
ServicesDependedOn  : {}
CanPauseAndContinue : False
CanShutdown         : False
CanStop             : False
ServiceType         : Win32ShareProcess

5.   
Comando
``` 
PS C:\Users\MateoML> ls -Path C:\ | Format-Wide -Column 4
```
Resultado
 Directory: C:\



.android                          adb                               AdwCleaner                       AMD                             
AplicacionesMoviles               dell                              Intel                            msx88                           
NVIDIA                            PerfLogs                          Program Files                    Program Files (x86)             
Steam                             User                              Users                            Windows                         
XiaoMi                            DEBUG.TXT                         eula.1028.txt                    eula.1031.txt                   
eula.1033.txt                     eula.1036.txt                     eula.1040.txt                    eula.1041.txt                   
eula.1042.txt                     eula.2052.txt                     eula.3082.txt                    globdata.ini                    
install.exe                       install.ini                       install.res.1028.dll             install.res.1031.dll            
install.res.1033.dll              install.res.1036.dll              install.res.1040.dll             install.res.1041.dll            
install.res.1042.dll              install.res.2052.dll              install.res.3082.dll             MiFlashvcom.ini                 
msdia80.dll                       vcredist.bmp                      VC_RED.cab                       VC_RED.MSI                      


6. 
Comando
```
PS C:\Users\MateoML> Get-ChildItem -Path C:\Windows | where -filter {$_.Name -like "*.exe"} | Format-List -Property Name, VersionInfo, @{Name='Size';Expression={$_.length}}
```

Resultado
Name        : bfsvc.exe
VersionInfo : File:             C:\Windows\bfsvc.exe
              InternalName:     bfsvc.exe
              OriginalFilename: bfsvc.exe.mui
              FileVersion:      6.1.7600.16385 (win7_rtm.090713-1255)
              FileDescription:  Utilidad de servicio de actualización del archivo de arranque
              Product:          Sistema operativo Microsoft® Windows®
              ProductVersion:   6.1.7600.16385
              Debug:            False
              Patched:          False
              PreRelease:       False
              PrivateBuild:     False
              SpecialBuild:     False
              Language:         Español (España, internacional)
              
Size        : 71168

Name        : d3bea6abc8a82889972f5c3f7eb56d51.exe
VersionInfo : File:             C:\Windows\d3bea6abc8a82889972f5c3f7eb56d51.exe
              InternalName:     
              OriginalFilename: 
              FileVersion:      
              FileDescription:  
              Product:          
              ProductVersion:   
              Debug:            False
              Patched:          False
              PreRelease:       False
              PrivateBuild:     False
              SpecialBuild:     False
              Language:         
              

7. 
Comando
*Resultado dado en el PC de mi hermano, pues aparece un error por no tener Windows 8 superior:
```
PS C:\Users\oscar> Import-Module NetAdapter

Ningún resultado!.

PS C:\Users\oscar> Get-NetAdapter | where -filter {$_.Virtual -eq $false} | Format-List
```

*Resultado  dado en el PC de mi hermano, pues aparece un error por no tener Windows 8 superior:

Name                       : Ethernet
InterfaceDescription       : Realtek PCIe GbE Family Controller
InterfaceIndex             : 6
MacAddress                 : 74-D4-35-99-AD-9D
MediaType                  : 802.3
PhysicalMediaType          : 802.3
InterfaceOperationalStatus : Up
AdminStatus                : Up
LinkSpeed(Mbps)            : 100
MediaConnectionState       : Connected
ConnectorPresent           : True
DriverInformation          : Driver Date 2015-04-10 Version 9.1.410.2015 NDIS 6.40

8.  
Comando
```
PS C:\Users\oscar>Import-Module DnsClient
```
Resultado: Ningun resultado!
Comando
```
PS C:\Users\oscar> Get-DnsClientCache | where -filter {$.Type -eq (28) -or $.Type -eq (1)} | Format-Table
```
Resultado

Entry                     RecordName                Record Status    Section TimeTo Data   Data                                                                          
                                                    Type                     Live   Length                                                                               
-----                     ----------                ------ ------    ------- ------ ------ ----                                                                          
safebrowsing.googleapi... safebrowsing.googleapi... A      Success   Answer      64      4 216.58.222.234                                                             
www.gstatic.com           www.gstatic.com           A      Success   Answer      63      4 172.217.172.3                                                                 
ogs.google.com            www3.l.google.com         A      Success   Answer      68      4 172.217.30.206                                                                
android.clients.google... android.l.google.com      A      Success   Answer      64      4 216.58.222.238                                                                
android.clients.google... android.l.google.com      A      Success   Answer      64      4 172.217.28.110                                                                
android.clients.google... android.l.google.com      A      Success   Answer      64      4 172.217.30.206                                                                
android.clients.google... android.l.google.com      A      Success   Answer      64      4 172.217.172.14                                                                
android.clients.google... android.l.google.com      A      Success   Answer      64      4 216.58.222.206                                                                
r4---sn-cvb7ln7l.googl... r4.sn-cvb7ln7l.googlev... A      Success   Answer     192      4 173.194.136.186                                                               
ota.nvidia.com            cs801.adn.phicdn.net      A      Success   Answer    1622      4 152.195.55.219                                                                
play.google.com           play.google.com           A      Success   Answer      64      4 216.58.222.238                                                                
oauthaccountmanager.go... oauthaccountmanager.go... A      Success   Answer      10      4 172.217.172.10

9.
Comando

```
PS C:\Users\MateoML> Get-ChildItem -Path C:\Windows\System32 | where -filter {$_.Name -like "*.exe" -and $_.length/1MB -gt 5} | Format-Table
```

Resultado

    Directory: C:\Windows\System32


Mode                LastWriteTime         Length Name                                                                                
----                -------------         ------ ----                                                                                
-a----     14/09/2019  01:12 p.m.        5904856 GfxUI.exe                                                                           
-a----     13/07/2009  08:39 p.m.        6676480 mspaint.exe                                                                         
-a----     02/02/2015  10:34 p.m.        5554104 ntoskrnl.exe                                                                        


10. 

Comando
```
PS C:\Users\MateoML> Get-HotFix | where -filter {$_.description -like "*security*"} | Format-List
```

Resultado:

  Description         : Security Update
FixComments         : 
HotFixID            : KB3033929
InstallDate         : 
InstalledBy         : MateoML-PC\MateoML
InstalledOn         : 19/02/2020 12:00:00 a.m.
Name                : 
ServicePackInEffect : 
Status              : 

11.

Comando
```
PS C:\Users\MateoML> Get-HotFix | where -filter {$_.installedBy -like "*SYSTEM*"} |Format-List
```
Resultado:
Description         : Security Update
FixComments         : 
HotFixID            : KB3033929
InstallDate         : 
InstalledBy         : MateoML-PC\MateoML
InstalledOn         : 19/02/2020 12:00:00 a.m.
Name                : 
ServicePackInEffect : 
Status              : 




PS C:\Users\MateoML> 
PS C:\Users\MateoML> 
PS C:\Users\MateoML> Get-HotFix | where -filter {$_.installedBy -like "*SYSTEM*"} |Format-List


Description         : Update
FixComments         : 
HotFixID            : KB2685811
InstallDate         : 
InstalledBy         : NT AUTHORITY\SYSTEM
InstalledOn         : 23/02/2017 12:00:00 a.m.
Name                : 
ServicePackInEffect : 
Status              : 



12.

Comando
```
PS C:\Users\MateoML> Get-Process | where -filter {$_.Name -eq "Conhost" -or $_.Name -eq "Svchost"} | Format-List
```
Resultado:

Id      : 2660
Handles : 35
CPU     : 0,0312002
SI      : 1
Name    : conhost

Id      : 136
Handles : 938
CPU     : 
SI      : 0
Name    : svchost

Id      : 452
Handles : 1508
CPU     : 
SI      : 0
Name    : svchost

1. 
   Comando  
   ```
   PS C:\Users\MateoML> Get-CimInstance win32_networkadapterconfiguration | Select-Object IP
   ```   
Resultado
   
Description             : WAN Miniport (IP)
Index                   : 8
IPAddress               : 
IPConnectionMetric      : 
IPEnabled               : False
IPFilterSecurityEnabled : 

Description             : Dispositivo Bluetooth (Red de área personal)
Index                   : 9
IPAddress               : 
IPConnectionMetric      : 
IPEnabled               : False
IPFilterSecurityEnabled : 

Description             : RAS Async Adapter
Index                   : 10
IPAddress               : 
IPConnectionMetric      : 
IPEnabled               : False
IPFilterSecurityEnabled : 

Description             : Adaptador ISATAP de Microsoft
Index                   : 11
IPAddress               : 
IPConnectionMetric      : 
IPEnabled               : False
IPFilterSecurityEnabled : 

Description             : Intel(R) Centrino(R) Wireless-N 1030
Index                   : 12
IPAddress               : {192.168.100.9, fe80::591f:b302:8b07:5141}
IPConnectionMetric      : 25
IPEnabled               : True
IPFilterSecurityEnabled : False

2.
   Comandos
   ```
  PS C:\Users\MateoML> Get-WmiObject win32_quickfixengineering
   ```   
   Resultado
  
  
Source        Description      HotFixID      InstalledBy          InstalledOn              
------        -----------      --------      -----------          -----------              
MATEOML-PC    Update           KB3191566     MateoML-PC\MateoML   19/02/2020 12:00:00 a.m. 
MATEOML-PC    Update           KB2533623     MateoML-PC\MateoML   09/02/2020 12:00:00 a.m. 
MATEOML-PC    Update           KB2685811     NT AUTHORITY\SYSTEM  23/02/2017 12:00:00 a.m. 
MATEOML-PC    Update           KB2809215     MateoML-PC\MateoML   19/02/2020 12:00:00 a.m. 
MATEOML-PC    Hotfix           KB2872035     MateoML-PC\MateoML   19/02/2020 12:00:00 a.m. 
MATEOML-PC    Update           KB2999226     MateoML-PC\MateoML   06/03/2017 12:00:00 a.m. 
MATEOML-PC    Security Update  KB3033929     MateoML-PC\MateoML   19/02/2020 12:00:00 a.m. 
MATEOML-PC    Update           KB4019990     MateoML-PC\MateoML   15/07/2019 12:00:00 a.m. 
MATEOML-PC    Update           KB976902      MateoML-PC\Admini... 21/11/2010 12:00:00 a.m. 
   
   
3. 
Comando
   ```
   PS C:\Users\MateoML> Get-WmiObject win32_service | Select-Object Status, Startmode, Systemname
   ```
   Resultado
Status Startmode Systemname
------ --------- ----------
OK     Auto      MATEOML-PC
OK     Manual    MATEOML-PC
OK     Auto      MATEOML-PC
OK     Manual    MATEOML-PC
OK     Manual    MATEOML-PC
OK     Manual    MATEOML-PC
OK     Disabled  MATEOML-PC
OK     Auto      MATEOML-PC
OK     Auto      MATEOML-PC
OK     Manual    MATEOML-PC
OK     Manual    MATEOML-PC
OK     Manual    MATEOML-PC
OK     Auto      MATEOML-PC
OK     Auto      MATEOML-PC
OK     Auto      MATEOML-PC
OK     Auto      MATEOML-PC
OK     Auto      MATEOML-PC
OK     Manual    MATEOML-PC
OK     Manual    MATEOML-PC
   
   
4. 
   Comandos
   ```
   PS C:\Users\MateoML> Get-CimClass -Namespace root/SecurityCenter2 | where -Filter {$_.CimClassName -like "*product*"}
   ```
   
   Resultado
 NameSpace: ROOT/SecurityCenter2

CimClassName                        CimClassMethods      CimClassProperties                                                          
------------                        ---------------      ------------------                                                          
AntiSpywareProduct                  {}                   {displayName, instanceGuid, pathToSignedProductExe, pathToSignedReporting...
AntiVirusProduct                    {}                   {displayName, instanceGuid, pathToSignedProductExe, pathToSignedReporting...
FirewallProduct                     {}                   {displayName, instanceGuid, pathToSignedProductExe, pathToSignedReporting
   
5. 
Con el Antispyware Windows Defender  
   Comando
   ```
   PS C:\Users\MateoML> Get-CimInstance -Namespace root/SecurityCenter2 -ClassName AntiSpywareProduct | Select-Object DisplayName
   ```
Resultado

```   
DisplayName     
-----------     
Windows Defender
```
----------------------------------------------------------------------------------------------------------------
Sin antivirus alguno instalado  
   Comando
   ```
   PS C:\Users\MateoML> Get-CimInstance -Namespace root/SecurityCenter2 -ClassName AntiVirusProduct | Select-Object DisplayName
   ```
  Resultado: No arroja ningún resultado. En blanco.

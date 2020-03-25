1.

Comando
```
PS C:\Users\Desktop> Get-Process | Select-Object Name, ID, Responding | Format-Table -AutoSize
```

Resultado


2. 

Comando

```
PS C:\Users\Desktop> Get-Process | Format-Table Name, Id, @{Name='VM (MB)';Expression={$_.VM / 1MB -as [int]}}, @{Name='PM (MB)'; Expression={$_.PM / 1MB -as [int]}}
```
Resultado


3. 
  
Comando 
 
```
PS C:\Users\Desktop> Get-EventLog -List | Format-Table @{Name='LogName';Expression={$_.LogDisplayName}}, @{Name='Periodo de Retencion';Expression={$_.minimumRetentionDays}}
```
Resultado

4.

Comando
 ```   
PS C:\Users\Desktop> Get-Service | Sort-by Status | Format-List -GroupBy status
```

Resultado

5.
   
Comando
``` 
PS C:\Users\Desktop> ls -Path C:\ | Format-Wide -Column 4
```
Resultado

6. 

Comando

```
PS C:\Users\Desktop> Get-ChildItem -Path C:\Windows | where -filter {$_.Name -like "*.exe"} | Format-List -Property Name, VersionInfo, @{Name='Size';Expression={$_.length}}
```

Resultado

7. 

Comando

```
PS C:\Users\Desktop> Import-Module NetAdapter

PS C:\Users\Desktop> Get-NetAdapter | where -filter {$_.Virtual -eq $false} | Format-List
```

Resultado


8.  

Comando

```
PS C:\Users\Desktop> Import-Module DnsClient

PS C:\Users\Desktop> Get-DnsClientCache | where -filter {$_.Type -eq (28) -or $_.Type -eq (1)} | Format-Table
```

Resultado


9.

Comando

```
PS C:\Users\Desktop> Get-ChildItem -Path C:\Windows\System32 | where -filter {$_.Name -like "*.exe" -and $_.length/1MB -gt 5} | Format-Table
```

Resultado


10. 

Comando

```
Get-HotFix | where -filter {$_.description -like "*security*"} | Format-List
```

11.

Comando
```
Get-HotFix | where -filter {$_.installedBy -like "*SYSTEM*"} |Format-List
```

12.

Comando

```
Get-Process | where -filter {$_.Name -eq "Conhost" -or $_.Name -eq "Svchost"} | Format-List
```

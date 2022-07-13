# Send a Popup-Window with Massages
Diffrent ways to send a pop-up window with massages to remote uers/computers within the network you control. Only work for windows OS.

#1 Using PS and MSG.exe  
Copy the following codes into a PowerShell script file you created, and then run the script with priveleged permission.
```
Function sendMSG { 
	Param([Parameter(Mandatory=$true)]$computer, [Parameter(Mandatory=$true)]$message)
	Invoke-Command -ComputerName $computer -Credential (Get-Credential) -ScriptBlock { msg * /V /W /TIME:15 "$message" }
sendMSG
```

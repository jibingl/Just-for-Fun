# Send a Pop-up Window with a Massage
Diffrent ways to send uers/computers a pop-up window with a massage. Only work for windows OS.

#1 Using PS and MSG.exe
Copy the following codes into a PowerShell script file you created, and then run the script with priveleged permission.
```
Function send-msg { 
	Param([Parameter(Mandatory=$true)]$computer, [Parameter(Mandatory=$true)]$message)
	Invoke-Command -ComputerName $computer -Credential (Get-Credential) -ScriptBlock { msg * /V /W /TIME:15 "$message" }
send-msg
```

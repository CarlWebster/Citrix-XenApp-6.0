Before you can start using PowerShell to document anything in the XenApp 6 farm you first need to install the SDK and Citrix Group Policy commands. 



From your XenApp 6 server, go to http://tinyurl.com/XenApp6PSSD



Scroll down and click on Download XenApp 6 Powershell SDK Version 6.1.2 


Extract the file to C:\XA6SDK. 
Click Start, Run, type in C:\XA6SDK\XASDK6.0.exe and press Enter



Back in your Internet browser; go to http://tinyurl.com/XenApp6PSPolicies



Scroll down and click on Citrix.GroupPolicy.Commands.psm1



Save the file in two different places:



C:\Windows\System32\WindowsPowerShell\v1.0\Modules, in a new folder named Citrix.GroupPolicy.Commands



C:\Windows\SysWOW64\WindowsPowerShell\v1.0\Modules, in a new folder named Citrix.GroupPolicy.Commands



Click Start, All Programs, Citrix, XenApp Server SDK, Windows PowerShell with Citrix XenApp Server SDK



To prepare for processing the Citrix farm policies, type in import-module Citrix.GroupPolicy.Commands



If you use Configuration Logging, you will need to use a UDL file in order for the History section of the script to work.  
For an explanation, see http://tinyurl.com/CreateUDLFile.

The UDL file will need to be placed in the same folder as the XA6_Inventory.ps1 script.  The UDL file will need to be named XA6ConfigLog.udl.  
You will need to edit the UDL file and add  ;Password=ConfigLogDatabasePassword to the end of the last line in the file.  For example, here is mine (line is one line):

Provider=SQLOLEDB.1;Integrated Security=SSPI;Persist Security Info=False;User ID=administrator;Initial Catalog=XA6ConfigLog;Data Source=SQL;Password=abcd1234



How to use this script?



I saved the script as XA6_Inventory.ps1 (or XA6_Inventory_V2.ps1) in the C:\PSScripts folder. 

From the PowerShell prompt, change to the C:\PSScripts folder, or the folder where you saved the script. 


From the PowerShell prompt, type in:



.\XA6_Inventory.ps1 | out-file .\XA6Farm.doc and press Enter.



or



.\XA6_Inventory_V2.ps1 | out-file .\XA6Farm.doc and press Enter.



Open XA6Farm.doc in either WordPad or Microsoft Word


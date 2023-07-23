To set up the RenameComputer app in Intune, perform the following steps.

Create the Win32 app using the CMD tool provided. Have a folder with the script, Intune app tool and the CMD file.

Add the RenameComputer.intunewin app to Intune and specify the following command line:

powershell.exe -noprofile -executionpolicy bypass -file .\RenameComputer.ps1

To "uninstall" the app, the following can be used (for example, to get the app to re-install):

cmd.exe /c del %ProgramData%\Microsoft\RenameComputer\RenameComputer.ps1.tag

Specify the platforms and minimum OS version that you want to support.

For a detection rule, specify the path and file and "File or folder exists" detection method:

%ProgramData%\Microsoft\RenameComputer RenameComputer.ps1.tag

Deploy the app as a required app in the ESP phase as required

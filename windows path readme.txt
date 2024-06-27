Step-by-Step Guide to Register a Custom URL Scheme in Windows

1.	Open the Windows Registry Editor:
•	Press Win + R, type regedit, and press Enter.
2.	Navigate to HKEY_CLASSES_ROOT:
•	Expand HKEY_CLASSES_ROOT.
3.	Create a New Key:
•	Right-click on HKEY_CLASSES_ROOT, select New -> Key.
•	Name the new key with your custom protocol name, e.g., myapp.
4.	Set the Default Value:
•	Click on the newly created key (myapp).
•	Double-click the (Default) value in the right pane and set it to a descriptive name, e.g., My Custom App.
5.	URL Protocol Entry:
•	Right-click on the myapp key, select New -> String Value.
•	Name it URL Protocol.
•	Leave its value empty or set it to an empty string.
6.	Create the shell Key:
•	Right-click on the myapp key, select New -> Key.
•	Name the new key shell.
7.	Create the open Key:
•	Right-click on the shell key, select New -> Key.
•	Name the new key open.
8.	Create the command Key:
•	Right-click on the open key, select New -> Key.
•	Name the new key command.
9.	Set the Default Value of the command Key:
•	Click on the command key.
•	Double-click the (Default) value in the right pane.
•	Set it to the path of your executable, including any arguments. Use %1 as a placeholder for the URL argument, e.g., "C:\Path\To\YourApp.exe" "%1".

HKEY_CLASSES_ROOT
 └── myapp
     ├── (Default) = "My Custom App"
     ├── URL Protocol = ""
     └── shell
         └── open
             └── command
                 └── (Default) = "C:\Path\To\YourApp.exe" "%1"\



EXAMPLE
Windows Registry Editor Version 5.00

[HKEY_CLASSES_ROOT\myapp]
@="My Custom App"
"URL Protocol"=""

[HKEY_CLASSES_ROOT\myapp\shell]

[HKEY_CLASSES_ROOT\myapp\shell\open]

[HKEY_CLASSES_ROOT\myapp\shell\open\command]
@="\"C:\\Path\\To\\YourApp.exe\" \"%1\""
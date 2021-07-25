# Windows PowerShell for basic operations: 

Access Windows PowerShell [official documentation](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.management/?view=powershell-7.1 "Windows PowerShell Official Documentation") to see all the available commands.
## A. <u>Navigation Commands</u>:

1. Navigate one directory up: 
   
    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">(short cmd):</span> cd ..\
    <span style="color:white; font-weight:normal;"> (long cmd):</span> Set-Location -Path "..\"</pre>
    </span>

2. Get current location path: 
   
    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">(short cmd):</span> pwd
    <span style="color:white; font-weight:normal;"> (long cmd):</span> Get-Location</pre>
    </span>

3. Navigate to certain location path:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">(short cmd):</span> cd "C:\path\to\your\directory"
    <span style="color:white; font-weight:normal;"> (long cmd):</span> Set-Location -Path "C:\path\to\your\directory"</pre>
    </span>

4. Navigate to a subdirectory inside the current root directory:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">(short cmd):</span> cd ".\subdirectory"
    <span style="color:white; font-weight:normal;"> (long cmd):</span> Set-Location -Path ".\subdirectoryName"</pre>
    </span>

5. Retrieve a list of all the child items in a certain directory: 

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">(short cmd):</span> dir "C:\path\to\your\directory"
    <span style="color:white; font-weight:normal;"> (long cmd):</span> Get-ChildItem -Path "C:\path\to\your\directory"</pre>
    </span>

6. Retrieve a detailed information about a certain file or directory:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">(short cmd):</span> gi "C:\path\to\your\directory\(fileName)"
    <span style="color:white; font-weight:normal;"> (long cmd):</span> Get-Item -Path "C:\path\to\your\directory\(fileName)"</pre>
    </span>

## B. <u>Item Manipulation Commands</u>:

1. Open a file or directory at a certain location:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">(short cmd):</span> ii ".\path\to\directory\(fileName)"
    <span style="color:white; font-weight:normal;"> (long cmd):</span> Invoke-Item -Path ".\path\to\directory\(file_name)"</pre>
    </span>

2. Copy a certain file or directory (it copies only the directory and not the content of that directory) from one place to another one:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">(short cmd):</span> copy ".\directoryName1\(fileName)" -Destination ".\directoryName2"
    <span style="color:white; font-weight:normal;"> (long cmd):</span> Copy-Item -Path ".\directoryName1\(fileName)" -Destination ".\directoryName2"</pre>
    </span>

3. Move a certain file or directory (it moves also the content of that directory) from one place to another one:
    
    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">(short cmd):</span> move ".\directoryName1\(fileName)" -Destination ".\directoryName2"
    <span style="color:white; font-weight:normal;"> (long cmd):</span> Move-Item -Path ".\directoryName1\(fileName)" -Destination ".\directoryName2"</pre>
    </span>

4. Rename a certain file or directory:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">(short cmd):</span> ren ".\directoryName1\(fileName)" -NewName ".\newDirectoryName(newFileName)"
    <span style="color:white; font-weight:normal;"> (long cmd):</span> Rename-Item -Path ".\directoryName1\(fileName)" -NewName ".\newDirectoryName(newFileName)"</pre>
    </span>

5. Delete a certain file or directory:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">(short cmd):</span> del ".\directoryName1(fileName)"
    <span style="color:white; font-weight:normal;"> (long cmd):</span> Remove-Item -Path ".\directoryName1(fileName)"</pre>
    </span>

## C. <u>Create Items Commands</u>:

1. Create a new subdirectory inside the current root directory:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">(short cmd):</span> ni ".\subdirectoryName(fileName)" -ItemType "directory(file)"
    <span style="color:white; font-weight:normal;"> (long cmd):</span> New-Item -Path ".\subdirectoryName(fileName)" -ItemType "directory(file)"</pre>
    </span>

2. Create multiple files or subdirectories inside the current root directory:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">(short cmd):</span> ni ".\subdirectoryName(fileName)", ".\subdirectoryName1(fileName1)", ".\subdirectoryName2(fileName2)" -ItemType "directory(file)"
    <span style="color:white; font-weight:normal;"> (long cmd):</span> New-Item -Path ".\subdirectoryName(fileName)", ".\subdirectoryName1(fileName1)", ".\subdirectoryName2(fileName2)" -ItemType "directory(file)"</pre>
    </span>

3. Create a new file inside the current root directory with a certain value inside of it:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">(short cmd):</span> ni ".\" -Name "fileName" -ItemType "file"
    <span style="color:white; font-weight:normal;"> (long cmd):</span> New-Item -Path ".\" -Name "fileName" -ItemType "file" -Value "This is a test.`nThis is a new line test."</pre>
    </span>

## D. <u>Utilities Commands</u>:

1. Display all the previous Windows PowerShell commands inserted in the terminal:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">(short cmd):</span> history
    <span style="color:white; font-weight:normal;"> (long cmd):</span> Get-History</pre>
    </span>

2. Display help information regarding a certain command:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">(short cmd):</span> help -Name cmdName
    <span style="color:white; font-weight:normal;"> (long cmd):</span> Get-Help -Name cmdName</pre>
    </span>
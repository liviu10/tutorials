# WORKING WITH VISUAL STUDIO CODE

1. Add a folder to the current workspace: 

   * <span style="color:red; font-weight:bold;">File > Add Folder to Workspace</span>

2. Save the current workspace:

   * <span style="color:red; font-weight:bold;">File > Save workspace as</span>

3. Exclude a folder from the current workspace:

   * <span style="color:red; font-weight:bold;">File > Preferences > Settings</span>
   * Select Workspace settings and then search for <span style="color:red; font-weight:bold;">"files.exclude"</span>
   * Click on Add Pattern and then type in <span style="color:red; font-weight:bold;">"\**/subdirectoryName"</span>, where "**" us the root folder

4. Windows PowerShell commands for Visual Studio Code:

   * List of all the Visual Studio Code PowerShell Commands: 
      <span style="color:red; font-weight:bold;">
         code --help
      </span>
   * Information regarding all the installed extensions:
      <span style="color:red; font-weight:bold;">
         code --list-extensions
      </span>
   * Information regarding the version of the installed extensions:
      <span style="color:red; font-weight:bold;">
         code --show-versions
      </span>
   * Install or update a certain extension by extension id:
      <span style="color:red; font-weight:bold;">
         code --install-extension ms-vscode.powershell
      </span>
   * Uninstall a certain extension by extension id:
      <span style="color:red; font-weight:bold;">
         code --uninstall-extension ms-vscode.powershell
      </span>
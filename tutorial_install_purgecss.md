# Install PurgeCSS

To install [PurgeCSS](https://purgecss.com/CLI.html#installation "PurgeCSS - Tool to remove unused CSS") you just need to open Windows PowerShell and:

1. Run the following command to enable execution of policies and avoid receiving an error that says "execution of scripts is disabled on this system" - [more here](https://stackoverflow.com/questions/4037939/powershell-says-execution-of-scripts-is-disabled-on-this-system).

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">   (enable execution policy):</span> Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine
    <span style="color:white; font-weight:normal;"> (restrict execution policy):</span> Set-ExecutionPolicy -ExecutionPolicy Restricted -Scope LocalMachine</pre>
    </span>

2. Run the following commands to install PurgeCSS as global project dependency to purge unused CSS styles or to uninstall the purgecss package:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;"> (globally install purgecss):</span> npm install --global purgecss
    <span style="color:white; font-weight:normal;">  (purge unused css command):</span> purgecss --css pathToCSSFiles/main-styles.css --content pathToHTMLFiles/index.html --output pathToOutputCSSFiles/purged_styles.css
    <span style="color:white; font-weight:normal;">(uninstall purgecss package):</span> npm uninstall --global purgecss</pre>
    </span>
# Install PurgeCSS

To install [PurgeCSS](https://purgecss.com/CLI.html#installation "PurgeCSS - Tool to remove unused CSS") you just need to open Windows PowerShell and:

1. Run the following command to enable execution of policies and avoid receiving an error that says "execution of scripts is disabled on this system" - [more here](https://stackoverflow.com/questions/4037939/powershell-says-execution-of-scripts-is-disabled-on-this-system).

    <span style="color:red; font-weight:bold;">
        <pre>Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine</pre>
    </span>

    <span style="color:red; font-weight:bold;">
        <pre>Set-ExecutionPolicy -ExecutionPolicy Restricted -Scope LocalMachine</pre>
    </span>

2. Run the following command to install PurgeCSS as global project dependency:

    <span style="color:red; font-weight:bold;">
        <pre>npm install --global purgecss</pre>
    </span>

3. Run the following command to purge the unused CSS and output the new CSS file:

    <span style="color:red; font-weight:bold;">
        <pre>purgecss --css pathToCSSFiles/main-styles.css --content pathToHTMLFiles/index.html --output pathToOutputCSSFiles/purged_styles.css</pre>
    </span>

4. Run the following command to uninstall PurgeCSS as global project dependency:

    <span style="color:red; font-weight:bold;">
        <pre>npm uninstall --global purgecss</pre>
    </span>
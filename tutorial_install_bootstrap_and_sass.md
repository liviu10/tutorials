# Install Bootstrap v5.0 & SASS

To install [Bootstrap Framework](https://getbootstrap.com/docs/5.0/getting-started/download/ "Bootstrap v5.0 - Frontend Framework") and [SASS](https://sass-lang.com/install "SASS - CSS Pre-processor") you just need to open Windows PowerShell and:

<span style="color:red; font-weight:bold;">
    <pre>
<span style="color:white; font-weight:normal;">(install Bootstrap package):</span> composer require twbs/bootstrap:5.1.0
<span style="color:white; font-weight:normal;">    (globally install SASS):</span> npm install --global sass
<span style="color:white; font-weight:normal;"> (compile SCSS to CSS file):</span> sass --watch "pathToSCSSFile/main-styles.scss" "pathToCSSFile/main-styles.css"</pre>
</span>
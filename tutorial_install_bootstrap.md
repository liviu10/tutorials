# Install Bootstrap v4.5

To install [Bootstrap Framework](https://getbootstrap.com/docs/4.5/getting-started/download/#npm "Bootstrap v4.5 - Frontend Framework") you just need to open Windows PowerShell and type the following commands:

1. Install Bootstrap Framework as a npm package:

    <span style="color:red; font-weight:bold;">
        <pre>npm install bootstrap</pre>
    </span>

2. Install the Bootstrap's dependency - [jQuery v3.5.1](https://jquery.com/download/ "jQuery v3.5.1 - Bootstrap's dependency"):

    <span style="color:red; font-weight:bold;">
        <pre>npm install jquery</pre>
    </span>

3. Open <span style="font-style:italic; font-weight:bold;">package.json</span> from the root directory and add the following line:

    <span style="color:red; font-weight:bold;">
        <pre>"popper.js": "^1.16.1"</pre>
    </span>

4. Install all the packages via npm:

    <span style="color:red; font-weight:bold;">
        <pre>npm install</pre>
    </span>

5. Open <span style="font-style:italic; font-weight:bold;">webpack.mix.json</span> from the root directory and replace the content with the following lines:

    <span style="color:red; font-weight:bold;">
        <pre>mix.js('resources/js/app.js', 'public/js')
        .sass('resources/sass/app.scss', 'public/css', [
            //
        });</pre>
    </span>

6. Inside <span style="font-style:italic; font-weight:bold;">root > resources</span> directory, rename <span style="font-style:italic; font-weight:bold;">css</span> folder to <span style="font-style:italic; font-weight:bold;">scss</span> and <span style="font-style:italic; font-weight:bold;">app.css</span> to <span style="font-style:italic; font-weight:bold;">app.scss</span>.

7. Open <span style="font-style:italic; font-weight:bold;">app.scss</span> from <span style="font-style:italic; font-weight:bold;">root > resources > scss</span> and add the following line to import the bootstrap css library:

    <span style="color:red; font-weight:bold;">
        <pre>@import '~bootstrap/scss/bootstrap';</pre>
    </span>

8. Open <span style="font-style:italic; font-weight:bold;">bootstrap.js</span> from <span style="font-style:italic; font-weight:bold;">root > resources > js</span> and add the following lines to import the bootstrap javascript library just above <span style="font-style:italic; font-weight:bold;">"window.axios = require('axios');"</span>:

    <span style="color:red; font-weight:bold;">
        <pre>try {
        window.Popper = require('popper.js').default;
        window.$ = window.jQuery = require('jquery');
        require('bootstrap');
    } catch (e) {}</pre>
    </span>

9. Run the bellow command in Windows PowerShell to compile all the scss and javascript file. You can add new CSS styles and JavaScript scripts inside <span style="font-style:italic; font-weight:bold;">root > resources > scss</span> and <span style="font-style:italic; font-weight:bold;">root > resources > js</span>. To recompile all these changes, re-run this command in the terminal.

    <span style="color:red; font-weight:bold;">
        <pre>npm run watch</pre>
    </span>
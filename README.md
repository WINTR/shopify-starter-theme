# Shopify Starter Theme
================================================================

## Install shopify_theme Gem


*The Shopify theme gem is a command line tool that lets you make live changes to themes on your Shopify store. ~~If the command line is scary, check out the Desktop Theme Editor app.~~*

install gem: `gem install shopify_theme`

generate config.yml file (replace values): `theme configure api_key password store_url`

<https://github.com/Shopify/shopify_theme>

Or run `theme` to print them out.
<br/>
<br/>

=======================

[Gulp](http://gulpjs.com/) Assets Build
================================================================

Includes [CoffeeScript](http://coffeescript.org/), [Browserify](https://github.com/substack/node-browserify) for CommonJS-style module wrapping, [Backbone](http://backbonejs.org/) for structure,
[Stylus](http://learnboost.github.io/stylus/) for CSS pre-processing, sourcemaps for CSS and CoffeeScript,
[Handlebars](http://handlebarsjs.com/) for templating, live-reload for automatic page-refreshes during development and Mocha + PhantomJS for unit testing.

Project Setup
-------------
- Install Node
 - [Node.js Installer](http://nodejs.org/)
- Install Gulp globally
 - `sudo npm install -g gulp`
- Clone and cd into the repo
 - `git clone https://github.com/WINTR/gulp-frontend-scaffold.git && cd gulp-frontend-scaffold`
- Then install Gulp task dependencies
 - `npm install`

Development Tasks
-----------------

- For development: `gulp dev` then navigate to `http://localhost:3000` (or IP address).
- For deploy: `grunt build`

This concatinates and minifies all CoffeeScripts and SASS and moves the project into 'dist' for production deploy.

Bower
-----
Bower is used for client-side package management.  Packages installed via bower are then copied over to `vendor` via `grunt bower` and each time you run `grunt dev`.

- To search for packages
 - `bower search {package name}`
- To install a package
 - `bower install {package name} --save`
 - `gulp bower`
 - Add the path to the new lib into the `concat` task in `gulpfile.coffee` and save


Unit Testing
------------
Mocha is used as the default for unit tests.  Via grunt-mocha, unit tests can be run in both the terminal as well as the browser.

- To execute tests via PhantomJS
 - `gulp test`
- To test in browser
 - Run `gulp test`
 - Navigate to `test/html/index.html`
- When running `gulp dev`, tests are automatically re-run on save of either your source or your spec files and should trigger a reload in the browser.


A Few Notes on Folder Structure
-------------------------------

- **Assets** like **images**, **audio**, **webfonts**, **etc** are created in `src/assets` and will automatically be moved over to the **public** folder, mirroring the folder structure where they came from.
- **Html** in `html` will be copied over to the `public` root.  **The public directory never needs to be touched.**
- **Scripts** such as **CoffeeScript** and **JavaScript** are placed here and compiled over to public via **Browserify**.  For those not familiar, Browserify allows for "CommonJS" style modules to be required inside internal files.  Attachments to the global namespace are no longer needed, and dependencies are traced at compile-time. (Example:  `var MyClass = require('./path/to/MyClass')`)  See the Browserify website for more information.
- **Styles** is where **SASS** files go, and are compiled over to **public** on save.
- **Vendor** is where are vendor sources go, from both **Bower** (via `bower install {package}` and then `grunt bower`) as well as manually.  When changes are made to this directory, the **GruntFile** `concat` task should be updated to include the newly added files
- **Tests** is where your **Mocha** tests and their accompanying html are located.  When developing, test files are **continually evaluated** and, if need be, compiled into `test/spec/spec-runner.js` to be run in the **browser**.

<br/>

=======================

##Skeleton theme


The Skeleton theme is a simplified Shopify theme, to be used as a "blank slate" starting point for theme designers.

<b>Features:</b>
- Almost no theme settings. Ready to be customized any way you want. 
- Only ~500 lines of CSS including comments. 
- Despite its 500 lines of CSS code, it is responsive and has styled drop-down menus.
- Include SVG images to style select elements and cart icon.
- Commented code to teach you Liquid concepts in practice.

<b>Demo:</b>

- [Demo store](http://skeleton.myshopify.com/)

Designing a store for a client? Earn 20% revenue through our <a href="http://www.shopify.com/partners">Partner program<a/>.

Getting started
---------------------
1. <a href="https://github.com/Shopify/skeleton-theme/archive/master.zip">Download</a> the latest version
2. or clone the git repo: <code>git clone https://github.com/Shopify/skeleton-theme.git</code>

Basic structure
---------------
```
├── assets
│   └── Javascript, CSS, and theme images
├── config
│   └── custom Theme Settings
├── layout
│   ├── theme.liquid
│   └── optional alternate layouts
├── snippets
│   └── optional custom code snippets
├── templates
│   ├── 404.liquid
│   ├── article.liquid
│   ├── blog.liquid
│   ├── cart.liquid
│   ├── collection.liquid
│   ├── index.liquid
│   ├── page.liquid
│   ├── product.liquid
│   └── search.liquid
│   └── list-collections.liquid
```

Additional resources
---------------------
- <a href="http://meetup.shopify.com/">Free workshops</a>: Sign up for a free Shopify For Designers workshop in a city near you.
- <a href="http://docs.shopify.com/themes">Theme Documentation</a>: Learn more about Liquid and theme templates.
- <a href="http://apps.shopify.com/desktop-theme-editor">Desktop Theme Editor</a>: For Mac OS X users, we recommend our free app to sync theme files in development. 
- Need more help? Ask a question in our <a href="http://ecommerce.shopify.com/c/ecommerce-design"> Design Forums</a>.

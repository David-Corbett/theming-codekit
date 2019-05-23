# Modernizr
Modernizr is a small piece of JavaScript code that automatically detects the availability of next-generation web technologies in your user's browsers. Rather than blacklisting entire ranges of browsers based on “UA sniffing”, Modernizr uses feature detection to allow you to easily tailor your user's experiences based on the actual capabilities of their browser.
          
With this knowledge that Modernizr gives you, you can take advantage of these new features in the browsers that can render or utilize them, and still have easy and reliable means of controlling the situation for the browsers that cannot.

The more recent versions of Modernizr no longer provide a single, base modernizr.js file. This way the smallest file possible is provided, which means a faster website for your customers.

## Getting started
- Head over to the [Modernizr download](https://modernizr.com/download) page, select the features you want to use in your project. 
- Once you have done that, just hit the `Build` button
- Download or copy the configuration file from the build menu (under "Command Line Config"). This will give you a JSON file that should be placed in the `config/` directory to enable the Modernizr module to make your custom build. Detects can be added to and removed at any time during the product lifecycle by updating this file.
- `npm run modernizr`

The `npm build` script will always run the modernizr build script as one of the tasks for compiling code for the production environment. This ensures that any changes applied the `modernizr-config.json` are updated in the production build. If you are not using modernizr to detect browser capabilities, simply don't include the `js/modernizr.min.js` file in the head of the html for pages on your site.

## Further reading
Full documentation is provided on the [Modernizr website](https://modernizr.com/docs).

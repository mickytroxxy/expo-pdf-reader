expo-pdf-reader
===============

**A wrapper around [Xavier Carpentier](https://github.com/xcarpentier)'s
[rn-pdf-reader-js](https://github.com/xcarpentier/rn-pdf-reader-js) that
gracefully degrades in the web**

Simply import `PDFReader` from `'@hashiprobr/expo-pdf-reader'` instead of
`'rn-pdf-reader-js'`. In the web, the component gracefully degrades to an
[object](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object) that
uses the browser built-in PDF viewer if available. While much more limited, this
allows Expo to preview the app in a browser without errors.

This is for development purposes only. Projects that need a proper PDF viewer
for the web should use better solutions like
[React-PDF](https://github.com/wojtekmaj/react-pdf) instead.


Install
-------

With npm:

```
npm install react-native-webview expo-file-system expo-constants rn-pdf-reader-js @hashiprobr/expo-pdf-reader
```

With yarn:

```
yarn add react-native-webview expo-file-system expo-constants rn-pdf-reader-js @hashiprobr/expo-pdf-reader
```

With expo:

```
expo install react-native-webview expo-file-system expo-constants rn-pdf-reader-js @hashiprobr/expo-pdf-reader
```

If using Expo, add the module to `webpack.config.js`:

``` js
const createExpoWebpackConfigAsync = require('@expo/webpack-config');

module.exports = async function (env, argv) {
    const config = await createExpoWebpackConfigAsync({
        ...env,
        babel: {
            dangerouslyAddModulePathsToTranspile: [
                '@hashiprobr/expo-pdf-reader',
            ]
        },
    }, argv);
    return config;
};
```

If `webpack.config.js` does not exist, create it with:

```
expo customize:web
```

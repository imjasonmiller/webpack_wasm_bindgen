Repository is relevant to an issue with Webpack 5 and WebAssembly.

* Run `npm i` inside of the `www` directory.
* Run `npm run serve`.

After starting the server, this will give the following error in your browser's console:

```none
TypeError: can't access property "__wbindgen_malloc", _index_bg_wasm__WEBPACK_IMPORTED_MODULE_0__ is undefined
```

Oddly enough, the following for `index.js` _does_ appear to show the alert, but does nothing with the passed string to `fn greet()`:

```javascript
import * as wasm from "./pkg/index_bg.wasm";

async function main() {
  wasm.greet("42");
}

main();
```

# vue-trellis-test

This is a basic Vue app, created with `npm create vue@latest`, that works just
fine with `@sayari/trellis@0.6.0`.

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

Start the development server at `http://localhost:3150`:

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```


## Newer versions of Trellis

### 0.6.1

Attempting to install version 0.6.1 leads to an immediate "_Package subpath
'undefined' is not defined by "exports"..._" error when starting the server:

```
Error:   Failed to scan for dependencies from entries:
  /ROOT_PATH/trellis-test-repos/vue-trellis-test/index.html

  ✘ [ERROR] Package subpath 'undefined' is not defined by "exports" in /ROOT_PATH/trellis-test-repos/vue-trellis-test/node_modules/@sayari/trellis/package.json. [plugin vite:dep-scan]

    node_modules/esbuild/lib/main.js:1373:21:
      1373 │         let result = await callback({
           ╵                      ^

    at resolveDeepImport (file:///ROOT_PATH/trellis-test-repos/vue-trellis-test/node_modules/vite/dist/node/chunks/dep-bb8a8339.js:28778:19)
    at tryNodeResolve (file:///ROOT_PATH/trellis-test-repos/vue-trellis-test/node_modules/vite/dist/node/chunks/dep-bb8a8339.js:28453:20)
    at Context.resolveId (file:///ROOT_PATH/trellis-test-repos/vue-trellis-test/node_modules/vite/dist/node/chunks/dep-bb8a8339.js:28212:28)
    at Object.resolveId (file:///ROOT_PATH/trellis-test-repos/vue-trellis-test/node_modules/vite/dist/node/chunks/dep-bb8a8339.js:44276:64)
    at process.processTicksAndRejections (node:internal/process/task_queues:95:5)
    at async resolve (file:///ROOT_PATH/trellis-test-repos/vue-trellis-test/node_modules/vite/dist/node/chunks/dep-bb8a8339.js:44581:26)
    at async file:///ROOT_PATH/trellis-test-repos/vue-trellis-test/node_modules/vite/dist/node/chunks/dep-bb8a8339.js:44758:34
    at async requestCallbacks.on-resolve (/ROOT_PATH/trellis-test-repos/vue-trellis-test/node_modules/esbuild/lib/main.js:1373:22)
    at async handleRequest (/ROOT_PATH/trellis-test-repos/vue-trellis-test/node_modules/esbuild/lib/main.js:729:13)

  This error came from the "onResolve" callback registered here:

    node_modules/esbuild/lib/main.js:1292:20:
      1292 │       let promise = setup({
           ╵                     ^

    at setup (file:///ROOT_PATH/trellis-test-repos/vue-trellis-test/node_modules/vite/dist/node/chunks/dep-bb8a8339.js:44748:19)
    at handlePlugins (/ROOT_PATH/trellis-test-repos/vue-trellis-test/node_modules/esbuild/lib/main.js:1292:21)
    at buildOrContextImpl (/ROOT_PATH/trellis-test-repos/vue-trellis-test/node_modules/esbuild/lib/main.js:978:5)
    at Object.buildOrContext (/ROOT_PATH/trellis-test-repos/vue-trellis-test/node_modules/esbuild/lib/main.js:786:5)
    at /ROOT_PATH/trellis-test-repos/vue-trellis-test/node_modules/esbuild/lib/main.js:2186:68
    at new Promise (<anonymous>)
    at Object.context (/ROOT_PATH/trellis-test-repos/vue-trellis-test/node_modules/esbuild/lib/main.js:2186:27)
    at Object.context (/ROOT_PATH/trellis-test-repos/vue-trellis-test/node_modules/esbuild/lib/main.js:2026:58)
    at prepareEsbuildScanner (file:///ROOT_PATH/trellis-test-repos/vue-trellis-test/node_modules/vite/dist/node/chunks/dep-bb8a8339.js:44531:26)

  The plugin "vite:dep-scan" was triggered by this import

    script:/ROOT_PATH/trellis-test-repos/vue-trellis-test/src/components/Trellis.vue?id=0:5:23:
      5 │ import * as Force from '@sayari/trellis/layout/force';
        ╵                        ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
```


### 0.7.0-rc.13

Installing version `0.7.0-rc.13` also leads to the same error as version 0.6.1.

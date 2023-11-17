# nuxt-trellis-test

This is a basic Nuxt app, created with `npx nuxi@latest init`, that fails to
import the `WebGL` component of Trellis:

```
require() of ES Module /ROOT_PATH/trellis-test-repos/nuxt-trellis-test/node_modules/d3-color/src/index.js from /ROOT_PATH/trellis-test-repos/nuxt-trellis-test/node_modules/@sayari/trellis/renderers/webgl/utils.js not supported. Instead change the require of index.js in /ROOT_PATH/trellis-test-repos/nuxt-trellis-test/node_modules/@sayari/trellis/renderers/webgl/utils.js to a dynamic import() which is available in all CommonJS modules.

at Object. (./node_modules/@sayari/trellis/renderers/webgl/node.js:66:15)
at Object. (./node_modules/@sayari/trellis/renderers/webgl/index.js:52:14)
```

## Setup

Make sure to install the dependencies:

```bash
npm install
```

## Development Server

Start the development server on `http://localhost:3100`:

```bash
npm run dev
```

## Production

Build the application for production:

```bash
npm run build
```

Locally preview production build:

```bash
npm run preview
```

Check out the [deployment documentation](https://nuxt.com/docs/getting-started/deployment) for more information.

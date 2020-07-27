# Svelte Configuration For Snowpack without Jest

The official svelte configuration (app-scripts-svelte) includes jest by default.
Unfortunately, jest is using packages which have been depricated.
This is the same config, but modified to remove the need for jest.

## Note on using Typescript

The easiest way is probably to use the snowpack-template-svelte-ts git repo, which includes this package, and does the below configuration.

```
npx degit vaishnavsm/snowpack-template-svelte-ts svelte-ts-app
```


Generally, in order to use typescript properly with Svelte,

1) Install the typescript and svelte-preprocess packages as dev dependencies
   ```
    yarn add --dev svelte-preprocess typescript
    npm i -D svelte-preprocess typescript
   ```
2) Add a file called `svelte.config.js` and export a preprocess property as an instance of svelte-preprocess.
   ```
    const preprocess = require('svelte-preprocess')

    module.exports = {
      preprocess: preprocess()
    }
   ```
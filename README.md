# QuARCS - The Questionably Accurate Rush Calendar Scheduler

*Live website not yet hosted*

# Development info

**NOTE:** The following commands **MUST** be run within the `site/` directory:

## Project setup
```
yarn install
```

You'll also need to install Rust and `wasm-pack` to build the WebAssembly components of the website.  Instructions for installing `wasm-pack` can be found [here](https://rustwasm.github.io/wasm-pack/installer/).

### Compiles and hot-reloads for development
```
yarn serve
```

### Lints and fixes files
```
yarn lint
```

### Run e2e tests
To start a local test server running on the correct semester for the e2e tests run:
```
yarn test:serve
```
Once the server is up and running you can launch cypress and run the tests with:
```
yarn test:e2e
```
Or run it headlessly with:
```
yarn test:e2e:headless
```

# webpack5-issue

## Reproduction Steps

1. `git clone https://github.com/exKAZUu/webpack5-issue.git`
1. `cd webpack5-issue`
1. `node -v`

    ```
    v13.6.0
    ```

1. `npx -v`

    ```
    6.13.4
    ```

1. `yarn -v`

    ```
    1.21.1
    ```

1. `yarn install`
1. `yarn webpack4`

    ```
    Hash: 12564861068bc852e8e7
    Version: webpack 4.41.5
    Time: 64ms
    Built at: 2020/01/16 23:34:00
      Asset       Size  Chunks             Chunk Names
    main.js  998 bytes       0  [emitted]  main
    Entrypoint main = main.js
    [0] ./src/main.js 43 bytes {0} [built]
    [1] external "fs" 42 bytes {0} [built]
    {
      appendFile: [Function: appendFile],
      appendFileSync: [Function: appendFileSync],
      access: [Function: access],
      accessSync: [Function: accessSync],
      chown: [Function: chown],

    ... snip ...
    ```

1. `yarn webpack5`

    ```
    ✅ Compilation Results
    
    🌏 Version: 5.0.0-beta.12
    ⚒️  Built: Thu Jan 16 2020 23:32:29 GMT+0900 (日本標準時)
    ⏱  Compile Time: 229ms
    📂 Output Directory: /Users/exkazuu/Projects/webpack5-issue/dist
    
    ┌───────────────┬─────────────────────────────────────────────┬───────────────┐
    │ Build Status  │ Bundle Name                                 │ Bundle Size   │
    ├───────────────┼─────────────────────────────────────────────┼───────────────┤
    │ failed        │ main.js                                     │ 0 kb          │
    └───────────────┴─────────────────────────────────────────────┴───────────────┘
    ⬢ webpack: /Users/exkazuu/Projects/webpack5-issue/src/main.js
    
    ⬢ webpack: Module not found: Error: Can't resolve 'fs' in '/Users/exkazuu/Projects/webpack5-issue/src'
    
    internal/modules/cjs/loader.js:976
      throw err;
      ^
    
    Error: Cannot find module '/Users/exkazuu/Projects/webpack5-issue/dist/main.js'
        at Function.Module._resolveFilename (internal/modules/cjs/loader.js:973:15)
        at Function.Module._load (internal/modules/cjs/loader.js:855:27)
        at Function.executeUserEntryPoint [as runMain] (internal/modules/run_main.js:71:12)
        at internal/main/run_main_module.js:17:47 {
      code: 'MODULE_NOT_FOUND',
      requireStack: []
    }
    ```

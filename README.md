- `b/btest` depends on `a/liba`
- `tsc -b .` runs with no errors in both projects (build output is in `build/ts`)
- when running `mocha -r ts-node/register -r tsconfig-paths/register btest.spec.ts` in `b/btest` you get the following error:

```
TSError: ⨯ Unable to compile TypeScript:
../../a/liba/index.ts:1:28 - error TS2503: Cannot find namespace 'cheerio'.

1 export const repro = (foo: cheerio.Root) => {
                             ~~~~~~~

    at createTSError (C:\Users\trinitrotoluene\WebstormProjects\ts-node-repro\b\btest\node_modules\ts-node\src\index.ts:587:12)
    at reportTSError (C:\Users\trinitrotoluene\WebstormProjects\ts-node-repro\b\btest\node_modules\ts-node\src\index.ts:591:19)
    at getOutput (C:\Users\trinitrotoluene\WebstormProjects\ts-node-repro\b\btest\node_modules\ts-node\src\index.ts:921:36)    
    at Object.compile (C:\Users\trinitrotoluene\WebstormProjects\ts-node-repro\b\btest\node_modules\ts-node\src\index.ts:1189:32)
    at Module.m._compile (C:\Users\trinitrotoluene\WebstormProjects\ts-node-repro\b\btest\node_modules\ts-node\src\index.ts:1295:42)
    at Module._extensions..js (node:internal/modules/cjs/loader:1138:10)
    at Object.require.extensions.<computed> [as .ts] (C:\Users\trinitrotoluene\WebstormProjects\ts-node-repro\b\btest\node_modules\ts-node\src\index.ts:1298:12)
    at Module.load (node:internal/modules/cjs/loader:989:32)
    at Function.Module._load (node:internal/modules/cjs/loader:829:14)
    at Module.require (node:internal/modules/cjs/loader:1013:19)
    at require (node:internal/modules/cjs/helpers:93:18)
    at Object.<anonymous> (C:\Users\trinitrotoluene\WebstormProjects\ts-node-repro\b\btest\b.spec.ts:1:1)
    at Module._compile (node:internal/modules/cjs/loader:1109:14)
    at Module.m._compile (C:\Users\trinitrotoluene\WebstormProjects\ts-node-repro\b\btest\node_modules\ts-node\src\index.ts:1295:23)
    at Module._extensions..js (node:internal/modules/cjs/loader:1138:10)
    at Object.require.extensions.<computed> [as .ts] (C:\Users\trinitrotoluene\WebstormProjects\ts-node-repro\b\btest\node_modules\ts-node\src\index.ts:1298:12)
    at Module.load (node:internal/modules/cjs/loader:989:32)
    at Function.Module._load (node:internal/modules/cjs/loader:829:14)
    at Module.require (node:internal/modules/cjs/loader:1013:19)
    at require (node:internal/modules/cjs/helpers:93:18)
    at Object.exports.requireOrImport (C:\Users\trinitrotoluene\WebstormProjects\ts-node-repro\b\btest\node_modules\mocha\lib\esm-utils.js:54:18)
    at Object.exports.loadFilesAsync (C:\Users\trinitrotoluene\WebstormProjects\ts-node-repro\b\btest\node_modules\mocha\lib\esm-utils.js:73:20)
    at singleRun (C:\Users\trinitrotoluene\WebstormProjects\ts-node-repro\b\btest\node_modules\mocha\lib\cli\run-helpers.js:125:3)
    at Object.exports.handler (C:\Users\trinitrotoluene\WebstormProjects\ts-node-repro\b\btest\node_modules\mocha\lib\cli\run.js:366:5)
```
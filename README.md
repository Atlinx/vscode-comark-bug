# VSCode Comark Bug

Minimal reproduction to demo VSCode Comark not parsing `component-meta.mjs` correctly.

## Reproduction Steps

1. Open the project in VSCode on Windows and install dependencies.

    ```bash
    npm install
    ```

2. Open one of the `content/**.md` files
    - **Ex.** [`content/index.md`](content/index.md), [`content/page2.md`](content/page2.md)
3. Open the VSCode output tab, and navigate to `MDC - Markdown Componeents`
4. See the following error

    ```
    2026-06-22T17:03:10.560Z [info]: Activating MDC extension...
    2026-06-22T17:03:10.560Z [info]: Registering MDC folding provider...
    2026-06-22T17:03:10.560Z [info]: MDC folding provider registered.
    2026-06-22T17:03:10.560Z [info]: Registering MDC bracket matching...
    2026-06-22T17:03:10.561Z [info]: MDC bracket matching registered.
    2026-06-22T17:03:10.561Z [info]: Registering MDC formatters...
    2026-06-22T17:03:10.561Z [info]: MDC formatters registered.
    2026-06-22T17:03:10.562Z [info]: Fetching MDC component metadata and clearing cache...
    2026-06-22T17:03:10.760Z [info]: Attempting to read metadata file: c:\Users\Demo\vscode-comark-bug\.nuxt\component-meta.mjs
    2026-06-22T17:03:10.764Z [info]: Processing local metadata from: c:\Users\Demo\vscode-comark-bug\.nuxt\component-meta.mjs
    2026-06-22T17:03:10.764Z [info]: Direct JSON parse failed, checking for export pattern...
    2026-06-22T17:03:10.765Z [error]: Unable to process local metadata content from: c:\Users\Demo\vscode-comark-bug\.nuxt\component-meta.mjs
    2026-06-22T17:03:10.765Z [info]: No valid metadata found in available sources.
    2026-06-22T17:03:10.765Z [info]: Initial MDC component metadata fetch completed.
    ```

**Note:**
- The generated `component-meta.mjs` should look like
  - [sample\component-meta.d.ts](sample\component-meta.d.ts)
  - [sample\component-meta.mjs](sample\component-meta.mjs)
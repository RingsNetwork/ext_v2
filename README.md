<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://static.ringsnetwork.io/ringsnetwork_logo.png">
  <img alt="Rings Network" src="https://raw.githubusercontent.com/RingsNetwork/asserts/main/logo/rings_network_red.png">
</picture>

Rings Extension (This extension is under development)
===============


# ext-v2

- **Nodejs** >= v16.13.0
- **pnpm** >= v8
![image](https://github.com/RingsNetwork/ext_v2/assets/21095710/ffc59941-0cb7-48f5-bda7-2a09201bf616)

## Usage

### Folders

- `src` - main source.
  - `contentScript` - scripts and components to be injected as `content_script`
  - `background` - scripts for background.
  - `components` - auto-imported React components that shared in popup and options page.
  - `styles` - styles shared in popup and options page
  - `manifest.ts` - manifest for the extension.
- `extension` - extension package root.
  - `assets` - static assets.
  - `dist` - built files, also serve stub entry for Vite on development.
- `scripts` - development and bundling helper scripts.

### Development

```bash
pnpm dev
```

Then **load extension in browser with the `extension/` folder**.

For Firefox developers, you can run the following command instead:

```bash
pnpm start:firefox
```

`web-ext` auto reload the extension when `extension/` files changed.

> While Vite handles HMR automatically in the most of the case, [Extensions Reloader](https://chrome.google.com/webstore/detail/fimgfedafeadlieiabdeeaodndnlbhid) is still recommanded for cleaner hard reloading.

### Build

To build the extension, run

```bash
pnpm build
```

And then pack files under `extension`, you can upload `extension.crx` or `extension.xpi` to appropriate extension store.

### Load || Install

To load the extension from source:

* Chrome:

https://developer.chrome.com/docs/extensions/mv3/getstarted/development-basics/#load-unpacked

* Firefox

In Firefox: Open the about:debugging page, click the This Firefox option, click the Load Temporary Add-on button, then select any file in your extension's directory.

ref: https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/Your_first_WebExtension

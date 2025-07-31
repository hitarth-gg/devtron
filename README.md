# Devtron

> [!NOTE]
> This project is under development and subject to change.
> Electron version 36.0.0 or later is required.

## Installation

- Install the package:

```bash
npm install @hitarth-gg/devtron --save-dev
```

- In your Electron app's `main.js` (or other relevant file) add the following code to load Devtron:

```js
//main.js
const { devtron } = require('@hitarth-gg/devtron');
// or import { devtron } from '@hitarth-gg/devtron'

devtron.install(); // call this function at the top of your file
```

- Devtron can be conditionally installed in **development mode** to avoid impacting production builds. Here's an example:

```js
const isDev = true

async function installDevtron() {
  const { devtron } = await import('@hitarth-gg/devtron')
  await devtron.install()
}

if (isDev) {
  installDevtron().catch((error) => {
    console.error('Failed to install Devtron:', error)
  })
}
```

## Requirements and Limitations

- Electron version must be 36.0.0 or higher.
- For Devtron to work with newly created **sessions**, you must call `devtron.install()` before they are created.
- IPC events sent before Devtron is installed (during early app startup) might not be captured.
- `ipcRenderer.once` will be tracked as two separate events `ipcRenderer.on` and then `ipcRenderer.removeListener`.

If Devtron is installed correctly, it should appear as a tab in the Developer Tools of your Electron app.

<img src="https://github.com/user-attachments/assets/0f278b54-50fe-4116-9317-9c1525bf872b" width="800">

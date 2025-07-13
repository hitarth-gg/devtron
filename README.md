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

or call `devtron.install()` inside the `app.whenReady()` callback like this:

```js
// main.js
const { devtron } = require('@hitarth-gg/devtron');
// or import { devtron } from '@hitarth-gg/devtron'

// function createWindow() {...}

app.whenReady().then(() => {
  devtron.install();
  // ...
});
```

- In your Electron app's `preload.js` (or other relevant file) add the following code to load Devtron:

```js
// preload.js
const { monitorRenderer } = require('@hitarth-gg/devtron/monitorRenderer');
// or import { monitorRenderer } from '@hitarth-gg/devtron/monitorRenderer'

monitorRenderer(); // call this function at the top of your file
```

If Devtron is installed correctly, it should appear as a tab in the Developer Tools of your Electron app.

<img src="https://github.com/user-attachments/assets/0f278b54-50fe-4116-9317-9c1525bf872b" width="800">

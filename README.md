# HypeTech - Prettier Configuration

The official HypeTech prettier configuration, part of Frontend Coding Standards.

> **Note**: Version 2.0.0+ requires Prettier 3.0.0 or higher. For Prettier 2.x, use version 1.x of this package.

## Installation

The configuration can be installed via package manager.

With PNPM:

```bash
## Preferred way
pnpm add @hypetech/prettier-config -D
```

With Yarn:

```bash
yarn add -D @hypetech/prettier-config
```

With NPM:

```bash
npm install --dev @hypetech/prettier-config
```

## Usage

### Method 1: package.json (Recommended for simple usage)

To inform prettier of this configuration, you have to add the `prettier` property to your `package.json` file:

```json
"prettier": "@hypetech/prettier-config"
```

Instead of manually editing your `package.json`, you can also utilize the `npm pkg` subcommand:

```bash
npm pkg set prettier=@hypetech/prettier-config
```

### Method 2: .prettierrc.js (Required for extending)

For Prettier 3, create a `.prettierrc.js` file:

```js
module.exports = require('@hypetech/prettier-config');
```

## Extending

To extend the configuration, you will have to create a `.prettierrc.js` file (or `.prettierrc.cjs` if your package is a `"type": "module"`) and import the HypeTech configuration:

```js
module.exports = {
    ...require('@hypetech/prettier-config'),
    // Your custom overrides
    semi: true,
}
```

## Configuration Details

This configuration includes the following settings:

- **semi**: `false` - No semicolons at the end of statements
- **singleQuote**: `false` - Use double quotes
- **printWidth**: `120` - Line wrap at 120 characters
- **tabWidth**: `4` - Use 4 spaces for indentation
- **quoteProps**: `"preserve"` - Only add quotes around object properties where necessary
- **endOfLine**: `"auto"` - Maintain existing line endings
- **trailingComma**: `"es5"` - Trailing commas where valid in ES5 (objects, arrays, etc.)

If you have previously added the configuration to your `package.json`, via the `prettier` property, you can now remove it.
You can also utilize the `npm pkg`:

```bash
npm pkg delete prettier
```

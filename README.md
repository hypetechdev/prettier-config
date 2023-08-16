# HypeTech - Prettier Configuration

The official HypeTech prettier configuration, part of Frontend Coding Standards.

## Installation

The configuration can be installed via package manager.

With PNPM:

```bash
## Preferred way
pnpm add @hypetech/prettier-config -D
```

With NPM:

```bash
npm install --dev @hypetech/prettier-config
```

With Yarn:

```bash
yarn add --dev @hypetech/prettier-config
```

To inform prettier of this configuration, you have to add the `prettier` property to your `package.json` file:

```json
"prettier": "@hypetech/prettier-config"
```

Instead of manually editing your `package.json`, you can also utilize the `npm pkg` subcommand:

```bash
npm pkg set prettier=@hypetech/prettier-config
```

## Extending

[Prettier does not ship with a built-in way of extending configurations](https://prettier.io/docs/en/configuration.html#sharing-configurations).

To extend the configuration, you will have to create a `.prettierrc.js` file (or `.prettierrc.cjs` if your package is a `"type": "module"`) and import the HypeTech configuration using `require`:

```js
module.exports = {
    ...require('@hypetech/prettier-config'),
    semi: true,
}
```

If you have previously added the configuration to your `package.json`, via the `prettier` property, you can now remove it.
You can also utilize the `npm pkg`:

```bash
npm pkg delete prettier
```

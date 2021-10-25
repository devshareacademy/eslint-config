# eslint-config

> Shared [Eslint config](https://eslint.org/) for my projects

## Install

```bash
yarn add -DE @swestover/eslint-config
```

**Note:** In order to use the package, you will need to have the peer dependencies that are listed installed in your project. You can add these dependencies by running the following command:

```bash
yarn add -D -E eslint @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint-config-prettier eslint-plugin-prettier prettier
```

## Usage

`.eslintrc`

```json
{
  "root": true,
  "extends": "@swestover/eslint-config",
  "parserOptions": {
    "project": "./tsconfig.json"
  },
  "rules": {}
}
```

## Publish New Version

```bash
# Authenticate with GitHub NPM Package Registry
npm login --scope=@scottwestover --registry=https://npm.pkg.github.com

# Run publish script
yarn package-publish
```

---

## Shared Configurations

- @scottwestover/eslint-config: [eslint-config](https://github.com/scottwestover/eslint-config)
- @scottwestover/tsconfig: [tsconfig](https://github.com/scottwestover/tsconfig)
- @scottwestover/prettier-config: [prettier-config](https://github.com/scottwestover/prettier-config)

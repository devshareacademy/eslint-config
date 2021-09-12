# eslint-config

> Shared [Eslint config](https://eslint.org/) for my projects

## Install

```bash
yarn add -DE @scottwestover/eslint-config
```

**Note:** In order to use the package, you will need to have the peer dependencies that are listed installed in your project. You can add these dependencies by running the following command:

```bash
yarn add -D -E eslint @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint-config-prettier eslint-plugin-prettier prettier
```

**Note:** In order to install this package, you will need to make sure `npm` is set to download `scottwestover` scoped packages from the GitHub Package Repository. More information on this can be found here: [GitHub Install Packages](https://docs.github.com/en/packages/learn-github-packages/installing-a-package).

## Usage

`.eslintrc`

```json
{
  "root": true,
  "extends": "@scottwestover/eslint-config",
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

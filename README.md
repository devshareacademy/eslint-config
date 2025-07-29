# eslint-config

> Shared [Eslint config](https://eslint.org/) for my projects

## Install

```bash
pnpm add -DE @devshareacademy/eslint-config
```

**Note:** In order to use the package, you will need to have the peer dependencies that are listed installed in your project. You can add these dependencies by running the following command:

```bash
pnpm add -D -E eslint typescript-eslint eslint-config-prettier eslint-plugin-prettier prettier globals @eslint/js
```

### Install Via GitHub NPM Packages

You can install this package from the GitHub NPM Package Repository. In order to do this, you must first authenticate with GitHub packages. You can read more about this process here: [GitHub - Installing A GitHub Package](https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-npm-registry#installing-a-package).

```bash
pnpm config set @lookio:registry https://npm.pkg.github.com/
echo "//npm.pkg.github.com/:_authToken=<github_personal_access_token>" > .npmrc
pnpm add -DE @devshareacademy/eslint-config
```

## Usage

`eslint.config.js`

```javascript
import eslintConfig from "@devshareacademy/eslint-config";

export default [
  {
    ignores: ["**/node_modules", "**/dist"],
  },
  ...eslintConfig,
  {
    languageOptions: {
      ecmaVersion: 5,
      sourceType: "script",
      parserOptions: {
        project: "./tsconfig.json",
      },
    },
    rules: {
      "@typescript-eslint/unbound-method": "off",
    },
  },
];
```

## Publish New Version

```bash
# Authenticate with NPM Package Registry
npm login

# Run publish script
yarn publish:npm
yarn publish:github
```

## Testing Changes Locally

### NPM Link

In order to test changes locally, you can can create a symlink to this npm package folder and then reference this folder in another project locally.

To create a symlink:

```bash
# run the following command from this projects directory
npm link
# change to the directory of the project you want to use this package in
cd ../../../some-other-project
# link-install the package
npm link @devshareacademy/connect-four
```

Please see the official documentation on [npm link](https://docs.npmjs.com/cli/v8/commands/npm-link) for more information.

### Verdaccio

Another option for testing changes locally is to use [Verdaccio](https://verdaccio.org/), which is a lightweight private proxy registry. With Verdaccio, you can publish this npm package to a local registry and then in another project you can install this package by pointing to the local registry.

There are a variety of ways to run Verdaccio, but in the following example we will be using [Docker](https://www.docker.com/).

#### Instructions

To setup and run Verdaccio:

```bash
docker run -it --rm --name verdaccio -p 4873:4873 verdaccio/verdaccio
```

To create a user and login:

```bash
npm adduser --registry http://localhost:4873
```

To publish a package:

```bash
npm publish --registry http://localhost:4873
```

To install the local package in another project:

```bash
NPM_CONFIG_REGISTRY=http://localhost:4873 npm install @devshareacademy/eslint-config
NPM_CONFIG_REGISTRY=http://localhost:4873 pnpm install @devshareacademy/eslint-config
```

---

## Shared Configurations

- @devshareacademy/eslint-config: [eslint-config](https://github.com/devshareacademy/eslint-config)
- @devshareacademy/tsconfig: [tsconfig](https://github.com/devshareacademy/tsconfig)
- @devshareacademy/prettier-config: [prettier-config](https://github.com/devshareacademy/prettier-config)

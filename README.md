# Indico ESLint config

This is the ESLint config used by the Indico team.

## Installation

```shell
npm install --save-dev eslint-config-indico
# if you use babel
npm install --save-dev eslint-plugin-babel babel-eslint
# if you use react
npm install --save-dev eslint-plugin-react
# if you use react-hooks
npm install --save-dev eslint-plugin-react-hooks
# if you use prettier
npm install --save-dev prettier eslint-plugin-prettier eslint-config-prettier
```

## Presets

### indico
The base config. You always want this when using this package.  
Requires `eslint-plugin-import`

### indico/react
Enables rules from the react plugin.  
Requires `eslint-plugin-react`

### indico/react
Enables rules from the react-hooks plugin.  
Requires `eslint-plugin-react-hooks`

### indico/babel
Enables the babel plugin and parser.  
Requires `eslint-plugin-babel` and `babel-eslint`.  
Make sure to load this *after* the `indico` preset to avoid duplicate quote warnings.

### indico/prettier
Enables prettier integration.  
Requires `prettier`, `eslint-config-prettier` and `eslint-plugin-prettier`  
Make sure to load this after all other `indico/*` presets.  
When using babel/react, also enable the `prettier/babel` and `prettier/react` presets.

For convenience, we also include a prettier config, that can be loaded by putting `"eslint-config-indico/prettier-config"` in your `.prettierrc`.

## Example `.eslintrc.yml`

```yaml
extends:
  - 'indico'
  - 'indico/babel'
  - 'indico/react'
  - 'indico/react-hooks'
  - 'indico/prettier'
  - 'prettier/babel'
  - 'prettier/react'

env:
  browser: true
  es6: true
```

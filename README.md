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


## Example `.eslintrc.yml`

```yaml
extends:
  - 'indico'
  - 'indico/babel'
  - 'indico/react'
  - 'indico/react-hooks'

env:
  browser: true
  es6: true
```

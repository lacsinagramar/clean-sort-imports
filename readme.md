# Clean Sort Imports
An eslint plugin that makes your imports readable. This is based on ESLint's [sort-imports](https://eslint.org/docs/rules/sort-imports) rule, the only thing that's different is the `memberSyntaxSortOrder` values.

Instead of `["none", "all", "multiple", "single"]` the values can be `["none", "all", "named", "default"]`.

The goal of this plugin is to achieve imports like this:
```javascript
import foo from 'foo'
import bar from 'bar'
import { Module1, Module2 } from 'modules'

import Asset1 from 'src/assets/asset1.jpg'
import Asset2 from 'src/assets/asset2.jpg'

import Button from 'src/components/Button'
import { List, ListItem } from 'src/components/List'
```
This way the imports look clean and organized.

## Installation
### Prerequisites
* You must have `eslint` package on your project `npm i eslint --save-dev` or `yarn add --dev eslint`

### Setup
* Install using yarn `yarn add --dev eslint-plugin-clean-sort-imports`
* Or using npm `npm i --save-dev eslint-plugin-clean-sort-imports`
* Add the following on your `.eslintrc`
    ```javascript
    "plugins": ["clean-sort-imports"],
    "rules": {
        "clean-sort-imports/clean-sort-imports": "error"
    }
    ```
* This will use the default configuration of this plugin

### Configuration
The default configuration is:
```javascript
{
    "ignoreCase": false,
    "ignoreDeclarationSort": false,
    "ignoreMemberSort": false,
    "memberSyntaxSortOrder": ["none", "all", "default", "named"],
    "allowSeparatedGroups": true
}
```
But you can configure it based on your preference.
Example:
```javascript
    "rules": {
        "clean-sort-imports/clean-sort-imports": ["error", {
            "ignoreCase": true,
            "ignoreDeclarationSort": false,
            "ignoreMemberSort": false,
            "memberSyntaxSortOrder": ["all", "default", "named", "none"],
            "allowSeparatedGroups": false
        }]
    }
```
Check ESLint's [sort-imports](https://eslint.org/docs/rules/sort-imports) for more info.

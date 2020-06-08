# @lwc/eslint-plugin-lwc

> Official ESLint rules for Lightning Web Components (LWC).

## Installation

```
$ npm install eslint babel-eslint @lwc/eslint-plugin-lwc --save-dev
```

## Usage

Add `lwc` to the `plugins` section of your configuration. Then configure the desired rules in the `rules` sections. Some of the syntax used in Lightning Web Components is not yet stage 4 (eg. decorators), and the out-of-the-box parser from ESLint doesn't support this syntax yet. In order to parse the LWC files properly, set the `parser` field to `babel-eslint`.

Example of `.eslintrc`:

```json
{
    "parser": "babel-eslint",
    "plugins": ["@lwc/eslint-plugin-lwc"],
    "rules": {
        "@lwc/lwc/no-deprecated": "error",
        "@lwc/lwc/valid-api": "error",
        "@lwc/lwc/no-document-query": "error"
    }
}
```

For more details about configuration please refer to the dedicated section in the ESLint documentation: https://eslint.org/docs/user-guide/configuring

## Configurations

To choose from three configuration settings, install the [`eslint-config-lwc`](https://github.com/salesforce/eslint-config-lwc) sharable configuration package.

## Rules

### LWC

| Rule ID                                                                                    | Description                                                       | Fixable |
| ------------------------------------------------------------------------------------------ | ----------------------------------------------------------------- | ------- |
| [lwc/consistent-component-name](./docs/rules/consistent-component-name.md)                 | ensure component class name matches file name                     | 🔧      |
| [lwc/no-api-reassignments](./docs/rules/no-api-reassignments.md)                           | prevent public property reassignments                             |         |
| [lwc/no-deprecated](./docs/rules/no-deprecated.md)                                         | disallow usage of deprecated LWC APIs                             |         |
| [lwc/no-document-query](./docs/rules/no-document-query.md)                                 | disallow DOM query at the document level                          |         |
| [lwc/no-leading-uppercase-api-name](./docs/rules/no-leading-uppercase-api-name.md)         | ensure public property doesn't start with an upper-case character |         |
| [lwc/no-unexpected-wire-adapter-usages](./docs/rules/no-unexpected-wire-adapter-usages.md) | enforce wire adapters to be used with `wire` decorator            |         |
| [lwc/no-unknown-wire-adapters](./docs/rules/no-unknown-wire-adapters.md)                   | disallow usage of unknown wire adapters                           |         |
| [lwc/valid-api](./docs/rules/valid-api.md)                                                 | validate `api` decorator usage                                    |         |
| [lwc/valid-track](./docs/rules/valid-track.md)                                             | validate `track` decorator usage                                  |         |
| [lwc/valid-wire](./docs/rules/valid-wire.md)                                               | validate `wire` decorator usage                                   |         |

### Best practices

| Rule ID                                                                  | Description                                 | Fixable |
| ------------------------------------------------------------------------ | ------------------------------------------- | ------- |
| [lwc/no-async-operation](./docs/rules/no-async-operation.md)             | restrict usage of async operations          |         |
| [lwc/no-dupe-class-members](./docs/rules/no-dupe-class-members.md)       | disallow duplicate class members            |         |
| [lwc/no-inner-html](./docs/rules/no-inner-html.md)                       | disallow usage of `innerHTML`               |         |
| [lwc/no-leaky-event-listeners](./docs/rules/no-leaky-event-listeners.md) | prevent event listeners from leaking memory |         |

### Compat performance

Older browsers like IE11 run LWC in compatibility mode. For more information about browser performance, please refer to [Supported Browsers](http://developer.salesforce.com/docs/component-library/documentation/lwc/lwc.get_started_supported_browsers) in the Lightning Web Components Developer Guide.

| Rule ID                                                    | Description                                 | Fixable |
| ---------------------------------------------------------- | ------------------------------------------- | ------- |
| [lwc/no-async-await](./docs/rules/no-async-await.md)       | disallow usage of the async-await syntax    |         |
| [lwc/no-for-of](./docs/rules/no-for-of.md)                 | disallow usage of the for-of syntax         |         |
| [lwc/no-rest-parameter](./docs/rules/no-rest-parameter.md) | disallow usage of the rest parameter syntax |         |

### Locker vNext best practices

| Rule ID                                                             | Description                       | Fixable |
| ------------------------------------------------------------------- | --------------------------------- | ------- |
| [locker/no-document-location](./docs/rules/no-document-location.md) | prevent `document.location` usage | 🔧      |
| [locker/no-dynamic-import](./docs/rules/no-dynamic-import.md)       | disallow dynamic import           |         |
| [locker/no-window-top](./docs/rules/no-window-top.md)               | prevent `window.top` usage        | 🔧      |

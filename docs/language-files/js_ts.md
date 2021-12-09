---
title: JS and TS
---

# JavaScript/TypeScript objects for localization

## ES6 and CommonJS modules are supported
```js
export default {
    key: 'Value',
    anotherKey: 'Another value',
    ...
    extracted: 'Extracted string will be added like this',
    ...
    some_key: {
        nested_key: 'Nested keys are also supported',
    },
    ...
    multiline: 'An explicitly multiline strings\nwill be extracted like this.'
}

// module.exports = {} is also supported
```

## Indentation
Configure formatting at the IDE level in [Preferences | Editor | Code Style | JSON](phpstorm://settings?name=Editor--Code+Style--JSON).

## Unsupported formats
Request support at [i18n-ally@lokalise.com](mailto:i18n-ally@lokalise.com).

#### Translations nested under some key are not supported
```js
{
    some_metadata: {
        'nonTranslationKey: true
    },
    translations: {
        key: 'This is NOT supported, because i18n Ally calls it like `translations.key` while the app would use just `key`'
    }
}
```

#### Complex key value is not supported
```js
{
    "other_key": {
        "translation": "Complex structure per key is NOT supported",
        "notes": ""
    }
}
```
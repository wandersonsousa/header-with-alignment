# Heading Tool

![Version of EditorJS that the plugin is compatible with](https://badgen.net/badge/Editor.js/v2.0/blue)

Provides Headings Blocks for the [Editor.js](https://ifmo.su/editor).

## Installation

### Install via NPM

Get the package

```shell
npm i --save editorjs-header-with-alignment
```

Include module at your application

```javascript
const Header = require("editorjs-header-with-alignment");
```

### Download to your project's source dir

1. Upload folder `dist` from repository
2. Add `dist/bundle.js` file to your page.

## Usage

Add a new Tool to the `tools` property of the Editor.js initial config.

```javascript
var editor = EditorJS({
  ...

  tools: {
    ...
    header: Header,
  },

  ...
});
```

## Config Params

All properties are optional.

| Field            | Type       | Description                 |
| ---------------- | ---------- | --------------------------- |
| placeholder      | `string`   | header's placeholder string |
| levels           | `number[]` | enabled heading levels      |
| defaultLevel     | `number`   | default heading level       |
| defaultAlignment | `string`   | default alignment level     |

```javascript
var editor = EditorJS({
  ...

  tools: {
    ...
    header: {
      class: Header,
      config: {
        placeholder: 'Enter a header',
        levels: [2, 3, 4],
        defaultLevel: 3,
        defaultAlignment: 'left'
      }
    }
  }

  ...
});
```

## Output data

| Field | Type     | Description                                          |
| ----- | -------- | ---------------------------------------------------- |
| text  | `string` | header's text                                        |
| level | `number` | level of header: 1 for H1, 2 for H2 ... 6 for H6     |
| align | `string` | heder alignment: 'left', 'center', 'justify', 'right |

```json
{
  "type": "header",
  "data": {
    "text": "Why Telegram is the best messenger",
    "level": 2,
    "align": "left"
  }
}
```

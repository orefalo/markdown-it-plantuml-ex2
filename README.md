# markdown-it-plantuml-ex2

[![npm version](https://img.shields.io/npm/v/markdown-it-plantuml-ex.svg)](https://www.npmjs.com/package/markdown-it-plantuml-ex)
[![CircleCI build](https://img.shields.io/circleci/project/github/xhinliang/markdown-it-plantuml-ex.svg)](https://circleci.com/gh/xhinliang/markdown-it-plantuml/tree/master)

> Plugin for creating block-level uml diagrams for [markdown-it](https://github.com/markdown-it/markdown-it) markdown parser using offline `plantuml.jar`.

Using this plugin and you can create uml diagrams inside your markdown files. 

Differ with [markdown-it-plantuml](https://github.com/gmunguia/markdown-it-plantuml), markdown-it-plantuml-ex use offline `plantuml.jar` to render your diagrams, that means three things:
1. You can safely use it in your secret project or some internal docs of your employer, because markdown-it-plantuml-ex **will not upload any of your data to any server**, it's totally offline;
2. You can enjoy a better render performance;
3. You should install Java by yourself before you start rendering, because markdown-it-plantuml-ex relies on it.

# UML example:

The diagrams you can use in your markdown file just like codes below.


    ```plantuml
    @startuml
    Bob -> Alice : hello
    @enduml
    ```

You can visit [plantuml website](https://plantuml.com) for more details.

## Installation

Just install via npm or any other package manager of Node.

```bash
$ npm i markdown-it-plantuml-ex2 --save
```

## Basic usage

As we all known, markdown-it-plantuml-ex2 is a plugin of markdown-it, so you should setup markdown-it before you use markdown-it-plantuml-ex2.

```js
import markit from "markdown-it";
import plantuml from "markdown-it-plantuml-ex2";
const md = markit();
md.use(plantuml);
```

See [markdown-it repository](https://github.com/markdown-it/markdown-it) for more details.

**NOTICE: You should install Java by yourself before you start rendering.**

## Advanced usage

```js
import markit from "markdown-it";
import plantuml from "markdown-it-plantuml-ex2";
const md = markit();
md.use(plantuml, options);
```

Options:
  - __openMarker__ - optional, defaults to "```plantuml". String to use as oppening delimiter.
  - __closeMarker__ - optional, defaults to "```" . String to use as closing delimiter.
  - __diagramName__ - optional, defaults to `uml`.
  - __render__ - optional, defaults to markdown-it image renderer. Renderer function for opening/closing tokens.
  - __javaPath__ - optional string path to the java application, defaults to `java`
  - __plantumlPath__ - optional string path to plantuml.jar, defaults to the internal

## License

[MIT](https://github.com/xhinliang/markdown-it-plantuml-ex/blob/master/LICENSE)

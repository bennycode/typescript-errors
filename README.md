# TypeScript Errors

## Motivation

TypeScript's strong type system allows for error detection during the design phase, rather than at runtime. This enables you to find bugs early in the development process.

While error messages may not always be straightforward, I have compiled a comprehensive guide of the most common TypeScript errors and how to solve them.

Feel free to contribute and provide solutions to yet unknown errors. All accepted pull requests appear online at [typescript.tv/errors/](https://typescript.tv/errors/).

## How to discover new errors

- Check these test cases (e.g. [callOverloads2.ts](https://github.com/microsoft/TypeScript/blob/main/tests/cases/compiler/callOverloads2.ts)) or test fixtures (e.g. [callOverloads2.errors.txt](https://github.com/microsoft/TypeScript/blob/main/tests/baselines/reference/callOverloads2.errors.txt)) from the official [TypeScript repository](https://github.com/microsoft/TypeScript)
- Try different compiler flags, especially the ones built for [type checking](https://www.typescriptlang.org/tsconfig#Type_Checking_6248) and starting with "no" (e.g. `noImplicitOverride`)
- List of [all error messages](https://github.com/microsoft/TypeScript/blob/main/src/compiler/diagnosticMessages.json)
- Matt Pocock's TypeScript error translator also has a list of [known errors](https://github.com/mattpocock/ts-error-translator/tree/main/packages/engine/errors)

## Writing sample code

There are two ways to write code examples for the different TypeScript errors: **Markdown Code Blocks** and **Hexo Code Blocks**.

### Markdown Code Blocks

You can use Markdown syntax to create [fenced code blocks](https://www.markdownguide.org/extended-syntax/#syntax-highlighting) with syntax highlighting:

````
```ts
function add(a: number, b: number): number {
  return a + b;
}
```
````

It also works for [JSX/TSX files](https://www.typescriptlang.org/docs/handbook/jsx.html):

````
```tsx
import React, {FC} from 'react';

const App: FC = (): JSX.Element => {
  return <></>;
};
```
````

### Hexo Code Blocks

The [Hexo.js Code Block](https://hexo.io/docs/tag-plugins.html#Code-Block) syntax is suggested when you desire to utilize features such as line highlighting or specifying the file name:

```
{% codeblock main.ts lang:ts mark:1,4-7 %}
console.log("My line will be marked.");
console.log("My line won't be marked.");
console.log("My line won't be marked as well.");
console.log("We will be marked.");
console.log("We will be marked.");
console.log("We will be marked.");
console.log("We will be marked.");
{% endcodeblock %}
```

### Format Markdown files

Formatting your Markdown content is as simple as running `npm run prettier`. This process will also be automatically performed when you commit staged files.

If you wish to prevent codeblocks from being formatted by Prettier, you can use the `<!-- prettier-ignore -->` directive:

````md
<!-- prettier-ignore-start -->
```ts
interface Animal {
  private name: string;
}
```
<!-- prettier-ignore-end -->
````

### Create internal links

From every post you can link to pages on [typescript.tv](https://typescript.tv/).

**Examples:**

```md
{% post_link error-ts2307-cannot-find-module-events 'Read more' %}
```

```md
More: {% post_link error-ts2307-cannot-find-module-events %}
```

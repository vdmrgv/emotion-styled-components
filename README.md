# emotion-styled-components

[![Version Badge][npm-version-svg]][package-url]
[![GZipped size][npm-minzip-svg]][bundlephobia-url]
[![Downloads][downloads-image]][downloads-url]
[![NPM total downloads][total-downloads-svg]][total-downloads-url]

A `styled` function with automatic filtering of non-standard attributes base on `@emotion/styled` package.<br />

### Motivation

`emotion-styled-components` is the result of thinking about how we could improve the forwarding of props for the `@emotion/styled` system. In one of our projects, we used the `styled-components` system, where the forwarding of props was provided out of the box, so when we switched to `@emotion/styled`, we encountered a problem when some components issued warnings: **"Invalid attribute name"**, and tried to solve this problem. By focusing on the use case of `styled-components`, we managed to solve this problem.

## Installation

To use this package you must have installed [emotion](https://emotion.sh/docs/install) package

```bash
  # with npm
  npm install --save emotion-styled-components @emotion/styled
```

```bash
  # with yarn
  yarn add emotion-styled-components @emotion/styled
```

## Simple Example

```js
import styled from 'emotion-styled-components';

const Button = styled(MyButton)<{ $primary?: boolean; }>`
  background: ${props => props.$primary ? "#BF4F74" : "white"};
  color: ${props => props.$primary ? "white" : "#BF4F74"};
`;

render(
  <div>
    <Button type="button">Normal</Button>
    <Button $primary type="submit">Primary</Button>
  </div>
);
```

> Note how the `$primary` prop is not passed to the DOM, but `type` are? The styled function is smart enough to filter non-standard attributes automatically for you.

It also supports all functions coming from [emotion](https://emotion.sh/docs/styled) by default

## Arguments

See more on [emotion](https://emotion.sh/docs/styled)

## Contributing

Please read through our [contributing guidelines](https://github.com/vdmrgv/emotion-styled-components/blob/main/CONTRIBUTING.md). Included are directions for opening issues, coding standards, and notes on development.

## License

Code released under the [MIT License][license-url].

[package-url]: https://npmjs.org/package/emotion-styled-components
[npm-version-svg]: https://img.shields.io/npm/v/emotion-styled-components.svg
[npm-minzip-svg]: https://img.shields.io/bundlephobia/minzip/emotion-styled-components.svg
[bundlephobia-url]: https://bundlephobia.com/result?p=emotion-styled-components
[license-url]: LICENSE
[downloads-image]: http://img.shields.io/npm/dm/emotion-styled-components.svg
[downloads-url]: http://npm-stat.com/charts.html?package=emotion-styled-components
[total-downloads-svg]: https://img.shields.io/npm/dt/emotion-styled-components.svg?style=flat
[total-downloads-url]: https://npmcharts.com/compare/emotion-styled-components?minimal=true


# emotion-styled-components

[![Version Badge][npm-version-svg]][package-url]
[![GZipped size][npm-minzip-svg]][bundlephobia-url]
[![Downloads][downloads-image]][downloads-url]
[![NPM total downloads][total-downloads-svg]][total-downloads-url]

A `styled` function with automatic filtering of non-standard attributes base on `@emotion/styled` package.<br />

### Motivation

`emotion-styled-components` is the result of thinking about how we can improve prop forwarding for the `@emotion/styled` system. In one of our past projects, we used the `styled-components` system where props forwarding was provided out of the box, but when we switched to `@emotion/styled` we ran into a problem where some components were generating warnings: `Invalid attribute name` then we tried to solve this problem. By focusing on the `styled-components` use case, we were able to solve this problem.

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

If the styled target is a simple element (e.g. `styled.div`), styled-components passes through any known HTML attribute to the DOM. If it is a custom React component (e.g. `styled(MyComponent)`), styled-components passes through all props.

This example shows how all props of the `Button` component are passed on to the DOM node that is mounted, as with React elements.

```js
import styled from 'emotion-styled-components';
import MyButton from '@my-ui-components';

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

It also supports all functions coming from [emotion](https://emotion.sh/docs/styled) by default.

## Arguments

See more on [emotion](https://emotion.sh/docs/styled).

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


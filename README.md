# react-universal-interface

[![][npm-badge]][npm-url] [![][travis-badge]][travis-url]

A `<Parent>` component that supports **universal component interface** provides all the following usage patters:

- FaCC &mdash; `<Parent>{(state) => <Child {...state} />}</Parent>`
- `render` prop &mdash; `<Parent render={(state) => <Child {...state} />} />`
- `component` prop &mdash; `<Parent component={Child} />` and `<Parent comp={Child} />`
- Prop injection &mdash; `<Parent><Child /></Parent>`
- `withState()` HOC
- `@withState` decorator

This library allows you to create components all the above interfaces.

- `renderChildren`
- `toEnhancer`

First, in your render method use `renderChildren`:

```js
class MyData extends Component {
    render () {
        return renderChildren(this.props, data);
    }
}
```

Second, create enhancer out of your component:

```js
const withData = toEnhancer(MyData, 'data');
```

Done!


## License

[Unlicense](./LICENSE) &mdash; public domain.


[npm-url]: https://www.npmjs.com/package/react-universal-interface
[npm-badge]: https://img.shields.io/npm/v/react-universal-interface.svg
[travis-url]: https://travis-ci.org/streamich/react-universal-interface
[travis-badge]: https://travis-ci.org/streamich/react-universal-interface.svg?branch=master

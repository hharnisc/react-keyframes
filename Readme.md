# React Keyframes

A React component for creating frame-based animations.

![Demo](https://cloud.githubusercontent.com/assets/775227/14613178/24789406-05d6-11e6-8411-6ee929ae3f3e.gif)

## Example

The following example will render contents in `Frame` one at a time every 500 ms.

```js
import { render } from 'react-dom';
import { KeyFrames, Frame } from 'react-keyframes';

render(
  <Keyframes>
    <Frame duration={500}>This</Frame>
    <Frame duration={500}>This is</Frame>
    <Frame duration={500}>This is <em>animated</em>.</Frame>
  </Keyframes>,
  document.getElementById('container')
);
```

## Documentation

### Installation

```js
$ npm install react-keyframes --save
```

### API

#### KeyFrames
**`<KeyFrames { component = 'span', delay = 0, onStart, onEnd } />`**

- Use `import { KeyFrames } from 'react-keyframes'` or `require('react-keyframes').KeyFrames`.
- The `component` prop specifies what component `KeyFrames` renders as.
- The `delay` prop specifies when the animation should start (millisecond).
- The `onStart` function is invoked upon animation start
- The `onEnd` function is invoked upon animation end
- Any additional, user-defined properties will become properties of the rendered component.
- It must have only `Frame` as children.
- Example:

  ```js
  import { Component } from 'react';
  import { Keyframes, Frame } from 'react-keyframes';

  class extends Component {
    render () {
      return <KeyFrames component="pre" delay={300} className="animation-test">
        <Frame>foo</Frame>
        <Frame>bar</Frame>
      </KeyFrames>;
    }
  }
  ```

#### Frame

**`<Frame { duration = 0 } />`**

- Use `import { Frame } from 'react-keyframes'` or `require('react-keyframes').Frame`.
- The `duration` prop specifies the length of time that a frame should show (millisecond).
- You have to put `Frame` in the order you want them animated.
- Example:

  ```js
  import { Component } from 'react';
  import { Keyframes, Frame } from 'react-keyframes';

  class extends Component {
    render () {
      return <KeyFrames>
        <Frame duration={100}>foo</Frame>
        <Frame duration={200}>bar</Frame>
      </KeyFrames>;
    }
  }
  ```

### Contributing

- Run `gulp help`  to see available tasks.
- Before submitting a PR, please run `gulp lint` and `npm test`.
- We use [`standard`](https://github.com/feross/standard) + semicolons.
- Please [be welcoming](http://contributor-covenant.org/).

## Credits

- Copyright © 2016 Zeit, Inc and project authors.
- Licensed under MIT.
- ▲

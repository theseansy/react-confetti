# react-confetti
Confetti without the cleanup. [Demo](http://alampros.github.io/react-confetti/)

Based on a pen by @Gthibaud: http://codepen.io/Gthibaud/pen/BoaBZK

[![demogif][2]][1]

[1]: http://alampros.github.com/react-confetti
[2]: http://alampros.github.io/react-confetti/confetti-demo.gif (demo gif)

## Install

```sh
npm i -S react-confetti
```

## Use

`width` and `height` props are required. Here, they are provided by [react-sizeme](https://github.com/ctrlplusb/react-sizeme):

```jsx
import PropTypes from 'prop-types'
import React from 'react'
import ReactDOM from 'react-dom'
import sizeMe from 'react-sizeme'
import Confetti from './react-confetti'

const DimensionedExample = sizeMe({
  monitorHeight: true,
  monitorWidth: true,
})(class Example extends React.PureComponent {
  static propTypes = {
    size: PropTypes.shape({
      width: PropTypes.number,
      height: PropTypes.number,
    }),
  }
  render() {
    return (
      <div style={{ position: 'absolute', top: 0, left: 0, width: '100%', height: '100%' }}>
        <Confetti {...this.props.size} />
      </div>
    )
  }
})

ReactDOM.render(<DimensionedExample />, document.getElementById('app'))
```

## Props

| Property         | Type                  | Default                                                                                                                                                                                                                                                                            | Description                                  |
| ---------------- | --------------------- | ---                                                                                                                                                                                                                                                                                | ---                                          |
| `width`          | `Number`              | `'100%'`                                                                                                                                                                                                                                                                           | Width of the `<canvas>` element.             |
| `height`         | `Number`              | `'100%'`                                                                                                                                                                                                                                                                           | Height of the `<canvas>` element.            |
| `numberOfPieces` | `Number`              | 200                                                                                                                                                                                                                                                                                | Number of confetti pieces at one time.       |
| `friction`       | `Number`              | 0.99                                                                                                                                                                                                                                                                               |                                              |
| `wind`           | `Number`              | 0                                                                                                                                                                                                                                                                                  |                                              |
| `gravity`        | `Number`              | 0.1                                                                                                                                                                                                                                                                                |                                              |
| `recycle`        | `Boolean`              | true                                                                                                                                                                                                                                                                               |                                              |
| `colors`         | `Array` of `String`   | `['#f44336'`</br>`'#e91e63'`</br>`'#9c27b0'`</br>`'#673ab7'`</br>`'#3f51b5'`</br>`'#2196f3'`</br>`'#03a9f4'`</br>`'#00bcd4'`</br>`'#009688'`</br>`'#4CAF50'`</br>`'#8BC34A'`</br>`'#CDDC39'`</br>`'#FFEB3B'`</br>`'#FFC107'`</br>`'#FF9800'`</br>`'#FF5722'`</br>`'#795548']`</br> | All available Colors for the confetti pieces |
| `opacity`        | `Number`              | 1.0                                                                                                                                                                                                                                                                                |                                              |

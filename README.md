# react-smooth-scrollbar

[smooth-scrollbar](https://github.com/idiotWu/smooth-scrollbar) for react projects.

## Requirements

React 0.14+

## Install

```
npm install react-smooth-scrollbar --save
```

## Demo

[http://idiotwu.github.io/react-smooth-scrollbar/](http://idiotwu.github.io/react-smooth-scrollbar/)

## Usage

```javascript
import React from 'react';
import ReactDOM from 'react-dom';
import Scrollbar from 'react-smooth-scrollbar';

class App extends React.Component {
    render() {
        return (
            <Scrollbar
                speed={Number}
                stepLength={Number}
                easingDuration={Number}
                easingCurve={String}
                propagation={Boolean}
            >
                your contents here...
            </Scrollbar>
        );
    }
}

ReactDOM.render(<App />, document.body);
```

### Available Options

| parameter | type | default | description |
| :--------: | :--: | :-----: | :----------: |
| speed | Number | 1 | Scrolling speed scale.|
| fricton | Number | 10 | Scrolling fricton, a percentage value within (1, 100) |
| inflection | Number | 10 | When scrolling speed is lower than infleciton point, sensitivity will be scaled to 10x. |
| sensitivity | Number | 0.1 | Wheel sensitivity, lower is accurate. |

Confusing with the option field? Try editor tool [here](http://idiotwu.github.io/smooth-scrollbar/)!


## Get Scrollbar Instance

1. Use `ref` in **parent component**:

    ```javascript
    class Parent extends React.Component {
        componentDidMount() {
            const { scrollbar } = this.refs.child;
        }

        render() {
            return (
                <Scrollbar ref="child">
                    your content...
                </Scrollbar>
            );
        }
    }
    ```

2. Use `Context` in **child component**:

    ```javascript
    class Child extends React.Component {
        static contextTypes = {
            getScrollbar: React.PropTypes.func
        };

        componentDidMount() {
            this.context.getScrollbar((scrollbar) => {
                // ...
            });
        }

        render() {
            return <div> this is child component. </div>;
        }
    }

    class App extends React.Component {
        render(){
            return (
                <Scrollbar>
                    <Child />
                </Scrollbar>
            );
        }
    }
    ```


## APIs

[Documents](https://github.com/idiotWu/smooth-scrollbar#apis)

## License

MIT.


### Hello World

`index.ios.js`
`index.android.js`

```js
"use strict";
import React, { Component } from "react";
import { AppRegistry, Text } from "react-native";

export default class HelloWorldApp extends Component {
  render() {
    return <Text>Hello world!</Text>;
  }
}

AppRegistry.registerComponent("MyApplication", () => HelloWorldApp);
```

---

```js
"use strict";
import React, { Component } from "react";

class Greeting extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

#### Declaring Default Props

```js
class Greeting extends React.Component {
  // ...
}

Greeting.defaultProps = {
  name: "Mary"
};
```

#### Setting the Initial State

```js
class Counter extends React.Component {
  constructor(props) {
    super(props);
    this.state = {count: props.initialCount};
  }
  // ...
}
```

```js
class SayHello extends React.Component {
  constructor(props) {
    super(props);
    this.state = { message: "Hello!" };
    // This line is important!
    this.handleClick = this.handleClick.bind(this);
  }

  handleClick() {
    alert(this.state.message);
  }

  render() {
    // Because `this.handleClick` is bound, we can use it as an event handler.
    return <button onClick={this.handleClick}>Say hello</button>;
  }
}
```

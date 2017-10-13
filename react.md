
```html
<script src="https://fb.me/react-0.14.3.js"></script>
<script src="https://fb.me/react-dom-0.14.3.js"></script>

<script src="https://fb.me/react-0.14.3.min.js"></script>
<script src="https://fb.me/react-dom-0.14.3.min.js"></script>
```

---

```html
<!doctype html>
<html>
  <head>
    <meta charset="utf-8">	
    <title>Hello React!</title>
     <script src="https://cdnjs.cloudflare.com/ajax/libs/react/0.13.3/react.min.js"></script>
     <script src="https://cdnjs.cloudflare.com/ajax/libs/react/0.13.3/JSXTransformer.js"></script>
  </head>
  <body>
    <div id="example"></div>

    <script type="text/jsx">
      React.render(
        <h1>Hello, world!</h1>,
        document.getElementById('example')
      );
    </script>
  </body>
</html>
```

```html
<!-- index.html -->
<!doctype html>
<html>
  <head>
    <meta charset="utf-8">	
    <title>Hello React</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/react/0.13.3/react.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/react/0.13.3/JSXTransformer.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.1.1/jquery.min.js"></script>
  </head>
  <body>
    <div id="content"></div>
    <script type="text/jsx">
      // Your code here
    </script>
  </body>
</html>
```

```jsx
var MyTextfield = React.createClass({
  render: function() {
    return <input type='text'/>;
  }
});

var MyButton = React.createClass({
  render: function() {
    return <button>{this.props.textlabel}</button>;
  }
});

React.render(<div>
  <MyTextfield/>
  <MyButton textlabel='OK'/>
</div>, document.getElementById('container'));
```

---

```
shell> bower install react --allow-root
```

```html
<!doctype html>
<html>
  <head>
    <meta charset="utf-8">	
    <title>Hello React!</title>
    <script src="build/react.js"></script>
    <script src="build/react-dom.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/babel-core/5.8.23/browser.min.js"></script>

  </head>
  <body>
    <div id="example"></div>
    <script type="text/babel">
      ReactDOM.render(
        <h1>Hello, world!</h1>,
        document.getElementById('example')
      );
    </script>
  </body>
</html>
```

```html
<!doctype html>
<html>
  <head>
    <meta charset="utf-8">	
    <title>Hello React!</title>
    <script src="build/react.js"></script>
    <script src="build/react-dom.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/babel-core/5.8.23/browser.min.js"></script>
  </head>
  <body>
    <div id="content"></div>
    <script type="text/babel">
    var CommentBox = React.createClass({
      render: function() {
        return (
          <div className="commentBox">
            Hello, world! I am a CommentBox.
          </div>
        );
      }
    });
    ReactDOM.render(
      <CommentBox />,
      document.getElementById('content')
    );
    </script>

  </body>
</html>
```

```
shell> npm install --global babel
shell> babel script.js --out-file script-compiled.js
shell> babel script.js --watch --out-file script-compiled.js
shell> babel src --watch --out-dir build
 ```

```html
<!doctype html>
<html>
  <head>
    <meta charset="utf-8">	
    <title>Hello React!</title>
    <script src="build/react.js"></script>
    <script src="build/react-dom.js"></script>
    <!-- No need for Babel! -->
  </head>
  <body>
    <div id="example"></div>
    <script src="build/helloworld.js"></script>
  </body>
</html>
```


#### :books: 參考網站：
- [babel](https://babeljs.io/docs/usage/cli/)

---

```jsx
var HelloWorld = React.createClass({
  render: function() {
    return <h1>Hello, world!</h1> ;
  }  
});

ReactDOM.render( <HelloWorld />, document.getElementById('example'));
```

```jsx
var Hello = React.createClass({
  render: function() {
    return <h1>Hello, {this.props.name}!</h1> ;
  }  
});

ReactDOM.render(<Hello name="羅得勝" />, document.getElementById('example'));
```

---

**main.js**

```js
var React = require('react');
var ReactDOM = require('react-dom');

ReactDOM.render(
  <h1>Hello, world!</h1>,
  document.getElementById('example')
);
```

```
shell> npm install --save react react-dom
shell> npm install -g browserify
shell> npm install babelify
shell> npm install reactify
shell> browserify -t reactify main.js -o build/helloworld.js
```

#### :books: 參考網站：
- [reactify](https://www.npmjs.com/package/reactify)
- [babelify](https://www.npmjs.com/package/babelify)

---

helloworld.js
```js
var React = require('react');

module.exports = React.createClass({
  render: function() {
    return <h1>Hello, world!</h1> ;
  }  
});
```

main.js
```js
var React = require('react');
var ReactDOM = require('react-dom');
var HelloWorld = require('./helloworld.js');

ReactDOM.render( <HelloWorld />, document.getElementById('example'));
```

```
shell> browserify -t reactify main.js -o build/helloworld.js
```

---

```jsx
var MyComponent = React.createClass({
  handleClick: function() {
   // window.alert("Hello world!");
   var input = this.refs.myInput;
   var inputValue = input.value;
   window.alert(inputValue);
  },

  render: function() {
    return (
      <div>
        <input ref="myInput" />
        <button type="submit" onClick={this.handleClick}>Submit</button>
      </div>
    );
  }
});
```

---

**test.jsx**
```jsx
var HelloMessage = React.createClass({
  render: function() {
    return <div>Hello {this.props.name}</div>;
  }
});

ReactDOM.render(<HelloMessage name="John" />, mountNode);
```

```
shell> babel test.jsx
```

---

#### :books: 參考網站：

- [企業應用Web 2.0必備的網頁技術](http://www.ithome.com.tw/node/44234)
- [react](http://facebook.github.io/react/)
- [getting-started](http://facebook.github.io/react/docs/getting-started.html)
- [tutorial](https://facebook.github.io/react/docs/tutorial.html)
- [react](https://facebook.github.io/react/downloads.html)

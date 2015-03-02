## React Scroll

Directive for basic scrolling and smooth scrolling ( work in progress )
Feel free to contribute - everything is appreciated

### Run
```js
$ npm install
$ npm run examples
```

### Usage
```js

var React = require('react');
var Scroll = require('react-scroll'); 

var Link = Scroll.Link;
var Element = Scroll.Element;

var Section = React.createClass({
  render: function () {
  	return (
		<Link to="test1" smooth={true}>Test 1</Link>
		<Link to="test2" smooth={true}>Test 2</Link>

		<Element name="test1" className="element">
		  test 1
		</Element>

		<Element name="test2" className="element">
		  test 2
		</Element>
	);
  }
});

React.render(
  <Section />,
  document.getElementById('example')
);

```

#### Create your own Link/Element
> Simply just include the mixins!

```js
var React = require('react');
var Helpers = require('../mixins/Helpers');

var Element = React.createClass({
  mixins: [Helpers.Element],
  render: function () {
    return (
      <div>
        {this.props.children}
      </div>
    );
  }
});

var Link = React.createClass({
  mixins: [Helpers.Scroll],
  render: function () {
    return (
      <a onClick={this.onClick} href="test">
        {this.props.children}
      </a>
    );
  }
});

```



### Todo
- [x] Vertical scrolling
- [x] Scroll to element
- [x] Smooth scroll animation
- [ ] Pass scroll/animation duration as settings
- [ ] Horizontal scrolling
- [ ] Spy on scrolling/Highlight
- [ ] Write test

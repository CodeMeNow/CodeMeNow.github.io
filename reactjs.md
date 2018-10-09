# ReactJS

## Index

1. Boilerplate for Bootstrapping a React component. `ReactDOM.render` will be used only once in the App at the top level.
```` javascript
import React from 'react';
import ReactDOM from 'react-dom';

const TestComponent = () => {
  return (<div class="test">Hello world</div>);
};

ReactDOM.render(<TestComponent />, document.getElementById('root'));
````
## References

1. [Pure React sample chapters](https://s3.amazonaws.com/daveceddia.com/Pure+React+-+sample+chapters.pdf)

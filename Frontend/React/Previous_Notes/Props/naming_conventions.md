# Props Naming Conventino

In React, when passing functions as props, it's a common convention to use names that start with "on" followed by the event or action you're handling. This helps make your code more readable and understandable, as it clearly indicates that the prop is a callback function.

For example:

```

// ParentComponent.jsx
import React from 'react';
import ChildComponent from './ChildComponent';

function ParentComponent() {
  const handleButtonClick = () => {
    console.log('Button clicked!');
  };

  return (
    <div>
      <ChildComponent onButtonClick={handleButtonClick} />
    </div>
  );
}

// ChildComponent.jsx
import React from 'react';

function ChildComponent({ onButtonClick }) {
  return (
    <button onClick={onButtonClick}>
      Click me
    </button>
  );
}

export default ChildComponent; 
```

In this example, the function handleButtonClick in the ParentComponent is passed to the ChildComponent as the prop onButtonClick.

 The "on" prefix suggests that this prop is a callback for an event, making it clear that it's a function meant to be triggered when a button is clicked.

While using "on" is a common convention, it's not mandatory, and you can choose meaningful names that suit your application's context. The key is to make your code readable and maintainable.

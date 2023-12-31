# Deleting Elements

To delete an element from an array in React state, you need to follow these steps:

1. Copy the Array: 

First, create a copy of the array from the state to avoid directly mutating the state. You should never modify the state directly in React.

2. Remove the Element: 

Use array methods like filter() to create a new array that excludes the element you want to delete.

3. Update the State: Set the state with the new array.

```
import React, { useState } from 'react';

function YourComponent() {
  // Step 1: Define your state with an array
  const [yourArray, setYourArray] = useState([1, 2, 3, 4, 5]);

  // Step 2 and 3: Remove an element and update the state
  
  const deleteElement = (elementToDelete) => {
    const newArray = yourArray.filter(item => item !== elementToDelete);
    setYourArray(newArray);
  };

  return (
    <div>
      <p>Array: {yourArray.join(', ')}</p>
      <button onClick={() => deleteElement(3)}>Delete 3</button>
    </div>
  );
}

export default YourComponent;

```


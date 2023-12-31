# Modifying Array States

In Javascript, we would just push this new object to the array. 
However, this won't work in React. React does not allow us to modify arrays directly.

# Adding Elements

1. Set up the array state and the updating function
2. Create a function to add an element
3. Use the updating function to add an element
4. Use the map function to loop through the array and display its elements.
5. Add a button to trigger adding an element

```
import React, { useState } from 'react';

function MyComponent() {

  // Step 1: Set up the array state and the function (setMyArray) to update it
  const [myArray, setMyArray] = useState([]);

  // Step 2: Create a function to add an element to the array
  const addItem = () => {
    // Step 3: Use the updating function to add an element to the array
    setMyArray([...myArray, 'New Element']);
  };

  return (
    <div>
      {/* Step 4: Display the array elements */}
      <ul>
        {myArray.map((item, index) => (
          <li key={index}>{item}</li>
        ))}
      </ul>

      {/* Step 5: Add a button to trigger adding an element */}
      <button onClick={addItem}>Add Element</button>
    </div>
  );
}

export default MyComponent;
```

### Modifying Array State

Here we will create a function to add the Item object into the array state.

```
  function handleAddItems(newItem) {
    setItems((currentItemsState) => [...currentItemsState, newItem]);
  }
```

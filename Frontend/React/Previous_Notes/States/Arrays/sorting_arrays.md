## Sorting Array States

## Alphabetically

```
import React, { useState } from 'react';

function YourComponent() {

  // Step 1: Define your state with an array
  const [yourArray, setYourArray] = useState(['banana', 'apple', 'grape', 'orange']);

  // Step 2 and 3: Sort the array alphabetically and update the state
  const sortAlphabetically = () => {
    const newArray = [...yourArray].sort();
    setYourArray(newArray);
  };

  return (
    <div>
      <p>Array: {yourArray.join(', ')}</p>
      <button onClick={sortAlphabetically}>Sort Alphabetically</button>
    </div>
  );
}

export default YourComponent;

```




## By Numbers

```
if (sortBy === "input") sortedItems = items;

  if (sortBy === "description")
    sortedItems = items
      .slice()
      .sort((a, b) => a.description.localeCompare(b.description));

  if (sortBy === "packed")
    sortedItems = items
      .slice()
      .sort((a, b) => Number(a.packed) - Number(b.packed));
```

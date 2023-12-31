# Adding Elements to an Array State

<p>In normal JS, we would just push this new object to the array. However, this won't work in React. React does not allow us to modify arrays directly.</p>


## Create the Array State in Parent

```
    const [medications, setMedications] = useState([]);

```

## Create an Add Item Function in Parent

```
  function handleAddItems(newItem) {
    setItems((currentItemsState) => [...currentItemsState, newItem]);
  }
```

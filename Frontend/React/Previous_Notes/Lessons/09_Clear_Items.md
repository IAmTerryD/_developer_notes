### Inside Packing List Create Button

      <div className="actions">
        <select value={sortBy} onChange={(e) => setSortBy(e.target.value)}>
          <option value="input">Sort by input order</option>
          <option value="description">Sort by name</option>
          <option value="packed">Sort by packed status</option>
        </select>
        <button onClick={onClearList}>Clear list</button>
      </div>
    </div>

### Create a Function to Clear the Array in Parent (App.js)

function handleClearList() {
setItems([]);
}

### Pass the Function to the Button

### Bonus: Create A Confirmation Popup

```
  function handleClearList() {
    const confirm = window.confirm('Are you sure you want to delete all items?'); // returns true or false

    if (confirm) {
      setItems([]);
    }
  }
```

<p>Confirm is part of the Browser API. We don't need anything special to use it.</p>


## Updating a Property State

<p>We want to modify isPacked boolean on an Item object when we click on a checkbox.</p>

```
function handleTogglePacked(itemID) {

    setItems((items) => { 
      // map through array state to find the item with the itemID
      items.map(item => item.id === itemID ? { ...item, packed: !item.packed } : item) })
  }
```
<p>
When the item ID is found, it modifies the item state. 
</p>


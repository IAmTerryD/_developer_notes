
# Adding Elements to an Array State

<p>In normal JS, we would just push this new object to the array. However, this won't work in React because <em>we are not modifying an array variable anymore</em>. We are modifying a state.
</p>

<p>That's why this section is so important. We will learn how to work with states which is vastly different than any regular variable in JS.</p>

### Modifying Array State

<p>Here we will create a function to add the Item object into the array state.</p>

```
  function handleAddItems(newItem) {
    setItems((currentItemsState) => [...currentItemsState, newItem]);
  }
```

## Deleting An Item from Array State

<p>
To delete the an item in the Items array state, we change the state.

> To modify a state, use the 'set' function.

We will create a function to remove an item from the item array state using filter:
</p>

```
  function handleDeleteItem(itemID) {
    setItems((items)=> items.filter(item=> item.id !== itemID));
  }
```
<small>
Filter removes the item with this ID from the array state and creates a new array state.
</small>

<p>
We have a function that changes the state in the parent App component. Great! Now how do we use it?
</p>

> We want this delete function to run every time we click on the red 'X'.

We should give this function to the X button, so that when we click the button this function runs. 

<p>
This button is located in the Item component.<br>
</p> 

> We have to send this function in the App component all the way to the button located inside the Items component. 

<p>
App > PacklingList > Item > Button
</p>

```
// App component passes the function:
<ItemList items={items} onDeleteItem={handleDeleteItem}/>

// ItemList component passes the function: 
<Item item={item} key={item.id} onDeleteItem={onDeleteItem} />

// Item component uses the function: 
<button onClick={() => onDeleteItem(item.id)}>❌</button>

```


## Updating a Object Property State

<p>We want to modify isPacked boolean on an Item object when we click on a checkbox.</p>

```
function handleTogglePacked(itemID) {
    setItems((items) => { 
      // map through array state to find the item with the itemID
      items.map(item => item.id === itemID ? { ...item, packed: !item.packed } : item) })
  }
```
<p>
When the item ID is found, it modifies the item state. We pass this function to the element that needs it, using same techniques from the prior example. 
</p>

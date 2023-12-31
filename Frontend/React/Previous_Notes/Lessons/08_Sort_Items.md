<p>
We want to allow users to sort the Items List by three different criteria.
</p>

# Packing List Component

## Create the State of the Select

```
const [sortBy, setSortBy] = useState("recent");
```

## Create the Select with onChange Event

```
      <div className='actions'>
        <select value={sortBy} onChange={e => setSortBy(e.target.value)}>
          <option value="recent">Sort Recent</option>
          <option value="alphabetically">Sort By Name</option>
          <option value="packed">Sort By Packed</option>
        </select>
      </div>
```

## Create a New Variable That will container a reorganized verison of an Array.

```
let sortedArray;
```

## Create conditional statements based on the variable.

By recent (Default)

```
  if (sortBy === 'recent') {
    sortedItems = items;
  }
```

By alphabetical order

```
  if (sortBy === 'alphabetically') {
    sortedItems = items.splice().sort((a, b) => a.description.localCompare(b.description));
  }

```

By Packed

```
  if (sortBy === 'packed') {
    sortedItems = items.slice().sort((a, b) => Number(a.packed) - Number(b.packed));
  }

```

# Display the sortedItem list rather than the Item list

```
    <div className="list">
      <ul>
        {sortedItems.map((item) => (
          <Item
            item={item}
            onDeleteItem={onDeleteItem}
            onToggleItem={onToggleItem}
            key={item.id}
          />
        ))}
      </ul>

```

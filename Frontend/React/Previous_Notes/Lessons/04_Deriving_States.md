<p>
This seems like it would be complicated based on everything we had to learn so far. But it's a simple concept.
</p>

## What is a Derived State

<p>In a practical sense, it just means getting basic data from a state using vanilla JS. That's really it.</p>

## Using Derived

<p>For example, we can get a length from an array state.</p>

```
export default function Stats({ items }) {

  const totalItems = items.length;

  return (
    <footer className='stats'>
      <em>You have X items on your list, and you already packed X</em>
    </footer>
  );
}

```

<p>When this component updates, it will rerun the items.length.</p>

<p>We will update Stats component with derived states.</p>

## Deriving States: Creating Sort Button

<p>
We will now create a feature that allows us to sort the items displayed from an array state. We will do this in the ItemList component.
</p>

First we create the HTML element:

```
      <select>
        <option value="recent">Sort Recent</option>
        <option value="alphabetically">Sort By Name</option>
        <option value="packed">Sort By Packed</option>
      </select>

```
<p>
Now that our element is created on the app, we need to know what option is selected by the user. 

In otherwords, we need React to take control of this element. This is something that we will do many times and we always do it in the same way. 
</p>

### Taking Control of Element with React

##### Create a State

```
const [sortBy, setSortBy] = useState("recent");
```

##### Use the State as the Value of the Element

```
      <select value={}>
        <option value="recent">Sort Recent</option>
        <option value="alphabetically">Sort By Name</option>
        <option value="packed">Sort By Packed</option>
      </select>
```

##### Attach the setState to the Element's EventListener

```
      <select value={sortBy} onChange={e=> setSortBy(e.target.value)}>
        <option value="recent">Sort Recent</option>
        <option value="alphabetically">Sort By Name</option>
        <option value="packed">Sort By Packed</option>
      </select>
```

<p>
Now that we let React control this item, everytime we change the select input, we see the Sort state change with it. Use the Dev Tools to see changes.
</p>

> How do we get the ItemList to display the sorted items?

<p>We will take the information from the array state and sort it based on our criteria.</p>

### Derived States - Part II
<
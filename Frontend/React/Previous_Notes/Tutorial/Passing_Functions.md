<p>
Will we often need Child components to change states. 
To change a state inside a Child component we will need to pass a function that alters the state. 

<strong>Do not pass the setState directly into a child directly.</strong>

</p>

##### Create a function inside Parent that Alters the state.

```
const [condition, setCondition] = useState("");

function handleSetCondition(newCondition) {
    setCondition(newCondition);
    console.log("Condition set to ", condition);
}

```

##### Pass the function into the Child component

```
 <Child handleChangeCondition={handleChangeCondition} />
```

##### Inside the Child, use the function passed.

```
export default function Child({handleChangeCondition}) {
    
    let disease = "hypertension";

    return (
        <button onClick={handleChangeCondition(disease)}>Change Condition</button>
    )
}

```
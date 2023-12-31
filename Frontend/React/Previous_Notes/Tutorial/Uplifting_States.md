## Uplifting States

<p>
We lift states in order to use a state in multiple components. We do this by placing the state in a Parent component.
</p>

##### Place the state we want multiple items to use in a Parent component.

```
function App() {
const [screen, setScreen] = useState("");
}
```

##### Pass the state into the components that we want it to be used in.

```
 <Selector screen={screen} />
```

##### Pass the set function into a component that we want to change this state.

<p>In this case, we use the same component.</p>

```
<Selector screen={screen} setScreen={setScreen} />
```

##### In the Child component, use the information passed to it from the Parent.

```
const Selector = ({ screen, setScreen }) => {

    return (
        <div className="row justify-content-center">
            <div className='col'>
                <span>Screen for <select value={screen} onChange={e => setScreen(e.target.value)}>
                    <option value="">any condition</option>
                    <option value="anxiety">anxiety</option>
                    <option value="depression">depression
                    </option>
                </select>.
                </span>
            </div>
        </div >
    );
}
```
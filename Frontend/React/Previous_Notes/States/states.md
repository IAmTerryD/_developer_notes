# React States 

In ReactJS, "state" is a JavaScript object that represents the current condition or data of a component. It's a way for a component to manage and keep track of information that can change over time. When the state of a component changes, React automatically re-renders the component, updating the user interface to reflect the new state.

# States, Like I'm Stupid

Imagine you're building a robot (a React component). A state is like the robot's brain. 
The robot's brain (state) keeps track of information it cares about. 
For example, it might keep track of whether it's happy or sad.

## 1. Initial State is like the starting point:

When you first build the robot, its initial state is set. It might start as a happy robot.
Changing State is like the robot reacting:

## 2. Change of state
If something happens, like you tell the robot a joke, its mood might change. This change in mood is like changing the state.

## 3. Re-rendering is like the robot expressing itself:

When the robot's mood changes, it expresses that change. In React, when the state changes, the component re-renders, showing the updated information on the screen.

```
import React, { useState } from 'react';

function Robot() {
  // Step 2: Setting up the initial state
  const [mood, setMood] = useState('happy');

  // Step 3: Changing the state
  const tellJoke = () => {
    setMood('laughing');
  };

  // Step 4: Re-rendering based on the state
  return (
    <div>
      <p>The robot is {mood}.</p>
      <button onClick={tellJoke}>Tell a Joke</button>
    </div>
  );
}

export default Robot;
```
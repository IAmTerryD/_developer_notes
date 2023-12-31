# Lifting State Up

Lifting state up in React is a way to manage shared state among multiple components by moving the state to a common ancestor component.

## ELI5

Imagine you have a family of components in React, like siblings (ChildComponent1 and ChildComponent2), and they want to share a toy (some data).

The Toy (Data):

Think of a toy as some information, like a number (let's call it "count").
Lifting Up (Sharing the Toy):

Instead of each sibling having their own copy of the toy, you give the toy to their parent (ParentComponent). Now, the parent holds the toy.
Passing Down (Sharing the Toy Again):

The parent (ParentComponent) can now decide who gets to play with the toy. It passes the toy down to each sibling as needed.
Playing with the Toy (Updating the Data):

When one sibling wants to change something about the toy (for example, increment the count), they tell the parent. The parent adjusts the toy, and because everyone is sharing the same toy, all the siblings see the change.

## Imagine Independent Components:

Picture several components on your page that need to share and synchronize the same piece of data.

1. Identify Shared State: 
Identify the state (data) that these components have in common, which needs to stay synchronized.

2. Move State Up: 
Instead of keeping the state in one of the components, move it up to the nearest common ancestor of those components. This common ancestor becomes the owner of the shared state.

3. Pass State Down as Props: 
The common ancestor component can pass the state down to its child components as props.

4. Update State in the Ancestor:
When any child component needs to update the shared state, it communicates with the common ancestor by invoking functions passed down as props.



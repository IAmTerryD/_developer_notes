# Async Functions

Imagine you're doing a series of tasks, and some of them take time, like making a sandwich or waiting for a friend to text back. 

Now, an async function in JavaScript is like telling your brain, "Hey, let's handle these tasks one by one, and I won't sit and wait for the slow ones. I'll let you know when they're done."


## Async Function Declaration:

When you declare a function as async, you're saying, "This function might take some time, and I won't block everything else while I'm working on it."
To declare a function as async, you use the async keyword before the function keyword.

```
async function myAsyncFunction() {
  // async function code here
}
```

## await Keyword:

Inside an async function, when you encounter something that takes time (like fetching data or waiting for a friend), you use the await keyword. 

It's like saying, "I'm going to pause here, but don't worry, I won't stop everything." It pauses the execution of the async function until the Promise is resolved, and then it resumes the function with the resolved value.

```
async function makeSandwich() {
  // Imagine fetching bread takes time
  const bread = await fetchBread();
  // Now, I can continue with other tasks while waiting for the bread
  spreadButter();
  addCheese();
}
```

In the example above, the await keyword is used with fetch and json methods, making the asynchronous code look more like synchronous code.


## Return a Promise:

An async function always returns a Promise. This is JavaScript's way of saying, "I'll let you know when I'm done, and you can do something with the result."

```
async function makeSandwich() {
  // Imagine fetching bread takes time
  const bread = await fetchBread();
  // Other tasks...
  return 'Sandwich is ready!';
}

makeSandwich().then(result => {
  console.log(result); // Output: Sandwich is ready!
});

```

## Error Handling:

You can use try and catch inside an async function just like regular synchronous code to handle errors.

```
async function makeSandwich() {
  try {
    const bread = await fetchBread();
    // Other tasks...
    return 'Sandwich is ready!';
  } catch (error) {
    console.error('Something went wrong:', error);
  }
}
```

In a nutshell, an async function is like telling JavaScript, "Hey, I'm going to do some things that might take time, but don't worry, I won't freeze everything. I'll let you know when I'm done, and we can keep going." It's a way to handle asynchronous tasks in a more readable and organized manner.


## Fetching from OMDB
```

KEY = '7241bc9b';

async function fetchData(title) {
  try {
    const response = await fetch(`http://www.omdbapi.com/?apikey=7241bc9b&t=${title}`);
    if (!response.ok) {
      throw new Error('Network response was not ok');
    }
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error('Error fetching data:', error);
  }
}

// Call the function to initiate the API request
fetchData("inception");

```

## Fetching from Postgres

```
const { Client } = require('pg');

const client = new Client({
  user: 'postgres',
  host: 'localhost',
  database: 'postgres',
  password: '12345',
  port: 5432, // Default PostgreSQL port
});

async function fetchData(table) {
  try {
    // Connect to database
    client.connect().then(() => {
      console.log('Connected to the database');
    });

    // Wait for the results
    await client.query(`SELECT * FROM ${table}`).then((result) => {
      console.log('Query result:', result.rows);
    });

    // Disconnect from database.
    client.end().then(() => {
      console.log('Connection to the database closed');
    });
  } catch (error) {
    console.error('Error: ', err);
  }
}

fetchData('users_profile');
```
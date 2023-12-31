# 1. Install CORS Header Package in Django Project

# 2. Run server in Django

# 3. Fetch Data 

```
import React, { useState, useEffect } from 'react';

const FetchData = () => {
    
  let [notes, setNotes] = useState([]);

  useEffect(() => {
    getNotes();
  }, []);

  let getNotes = async () => {
    # Location of API
    let response = await fetch('http://127.0.0.1:8000/api/notes/');
    
    # Convert API data to JSON
    let data = await response.json();
    
    console.log('Data: ', data);
    setNotes(data);
  };

  return <div>Notes</div>;
};

export default FetchData;

```

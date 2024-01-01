# Troubleshooting 

This is unique to Django.

React handles the urls when clicking on frontend links.

If you hard reset on a note page, it does not find the page. 

# What's happening?

Django looks at the urls.py, but cannot find the url in the default path.
The page loads to slow for Django to find in time.

# Fix

Using a hash router instead of BrowserRouter.

```
import { HashRouter as Router, Routes, Route } from 'react-router-dom';
```

# Other Fix

Server side rendering
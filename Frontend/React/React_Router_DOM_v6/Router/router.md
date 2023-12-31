# Router 

In React Router version 6, using the <Route> component has seen some changes compared to earlier versions. Here's a simple guide on how to use it:

# Basic Structure

In React Router v6, routes are defined within a <Routes> component, which replaces the <Switch> component used in earlier versions. The <Route> component is then used to define individual routes.

```
import Home from './Home';
import About from './About';
import NotFound from './NotFound';

function App() {
  return (
    <Router>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="about" element={<About />} />
        <Route path="*" element={<NotFound />} />
      </Routes>
    </Router>
  );
}
```

> "/": Renders the Home component.

> "/about": Renders the About component.

> *: A wildcard route for handling 404 or not found pages, rendering the NotFound component.

# Notes:
## Nested Routes: 
In v6, nested routes are more intuitive. 

You define nested routes within the component of the parent route, making it easier to understand the nesting structure.

## Relative Links: 
Links within a component are relative to the route the component is rendered in. This makes linking within nested routes more straightforward.

## No exact Prop: 
The exact prop from previous versions is no longer needed. In v6, routes are automatically exact.

## useParams, useNavigate, and other Hooks: 
React Router v6 continues to provide hooks like useParams and useNavigate for getting URL parameters and programmatically navigating, respectively.

React Router version 6 brings more intuitive routing with a simpler and more powerful API, making it easier to manage complex routing scenarios in your React applications.

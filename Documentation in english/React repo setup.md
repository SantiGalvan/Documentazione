# Creating a React Repository

## Creating a New React Project

To create a new React project with Vite, run the following command:

```sh
npm create vite@latest project-name --template react
```

If you want to open Visual Studio Code immediately:

```sh
code project-name
```

If you want to create the project in the current folder, use:

```sh
npm create vite@latest . --template react
```

and open Visual Studio Code with:

```sh
code .
```

---

## Starting the Development Server

To start the local server:

```sh
npm install  # Install dependencies
npm run dev  # Start the server (Vite)
```

Open your browser and visit **[http://localhost:5173](http://localhost:5173)** (Vite).

---

## Removing Default Values

1. Delete the `App.css` file.
2. Clear all content in `index.css`.
3. Remove all content in `App.jsx` and replace it with:

```jsx
const App = () => {
  return (
    <section>
        <h1>App</h1>
    </section>
  );
}

export default App;
```

---

## Installing React Router Dom

If you want to use navigation between pages in React, install `react-router-dom` with:

```sh
npm install react-router-dom
```

### Configuring React Router

To configure the router, modify the `main.jsx` file:

```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';
import { BrowserRouter } from 'react-router-dom';
import App from './App';
import './index.css';

ReactDOM.createRoot(document.getElementById('root')).render(
  <React.StrictMode>
    <BrowserRouter>
      <App />
    </BrowserRouter>
  </React.StrictMode>
);
```

---

## Defining Routes

In the `App.jsx` file, define routes using `Routes` and `Route`:

```jsx
import { Routes, Route } from 'react-router-dom';
import Home from './pages/Home';
import About from './pages/About';
import NotFound from './pages/NotFound';

const App = () => {
  return (
    <Routes>
      <Route path="/" element={<Home />} />
      <Route path="/about" element={<About />} />
      <Route path="*" element={<NotFound />} />
    </Routes>
  );
}

export default App;
```

---

## Creating Pages

Create the `pages` folder and add files for each page.

### `Home.jsx`

```jsx
function Home() {
  return (
    <section>
        <h1>Home Page</h1>
    </section>
  );
}

export default Home;
```

### `About.jsx`

```jsx
function About() {
  return (
    <section>
        <h1>About Page</h1>
    </section>
  );
}

export default About;
```

### `NotFound.jsx`

```jsx
function NotFound() {
  return (
    <section>
        <h1>404 - Page Not Found</h1>
    </section>
  );
}

export default NotFound;
```

---

## Installing Tailwind CSS

If you want to use Tailwind CSS in your project, install it with:

```sh
npm install tailwindcss @tailwindcss/vite
```

### Configuring Tailwind CSS

Modify `vite.config.js`:

```js
import { defineConfig } from 'vite'
import tailwindcss from '@tailwindcss/vite'
export default defineConfig({
  plugins: [
    tailwindcss(),
  ],
})
```

Modify `index.css`:

```css
@import "tailwindcss";
```

Now you can use Tailwind CSS in your project!

---

## Conclusion

Now you have a React project set up with:

- React Router for navigation
- Tailwind CSS for styling


# Creazione di un Repository React

## Creazione di un Nuovo Progetto React

Per creare un nuovo progetto React con Vite, esegui il seguente comando:

```sh
npm create vite@latest nome-progetto --template react
```

Se vuoi aprire subito Visual Studio Code:

```sh
code nome-progetto
```

Se desideri creare il progetto nella cartella attuale, usa:

```sh
npm create vite@latest . --template react
```

e apri subito Visual Studio Code con:

```sh
code .
```

---

## Avvio del Server di Sviluppo

Per avviare il server locale:

```sh
npm install  # Installa le dipendenze
npm run dev  # Avvia il server (Vite)
```

Apri il browser e visita **[http://localhost:5173](http://localhost:5173)** (Vite).

---

## Rimozione Valori di Default

1. Cancella il file `App.css`.
2. Cancella tutto il contenuto di `index.css`.
3. Rimuovi tutto il contenuto di `App.jsx` e sostituiscilo con:

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

## Installazione di React Router Dom

Se vuoi utilizzare la navigazione tra pagine in React, installa `react-router-dom` con:

```sh
npm install react-router-dom
```

### Configurazione di React Router

Per configurare il router, modifica il file `main.jsx`:

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

## Definizione delle Route

Nel file `App.jsx`, definisci le rotte utilizzando `Routes` e `Route`:

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

## Creazione delle Pagine

Crea la cartella `pages` e aggiungi i file per ogni pagina.

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

## Installazione di Tailwind CSS

Se vuoi usare Tailwind CSS nel tuo progetto, installalo con:

```sh
npm install tailwindcss @tailwindcss/vite
```

### Configurazione di Tailwind CSS

Modifica `vite.config.js`:

```js
import { defineConfig } from 'vite'
import tailwindcss from '@tailwindcss/vite'
export default defineConfig({
  plugins: [
    tailwindcss(),
  ],
})
```

Modifica `index.css`:

```css
@import "tailwindcss";
```

Ora puoi usare Tailwind CSS nel tuo progetto!

---

## Conclusione

Ora hai un progetto React configurato con:

- React Router per la navigazione
- Tailwind CSS per lo styling
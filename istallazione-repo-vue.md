# Istallazione Repo Vue (SASS, Bootstrap, FontAwesome, Fontsource)

### Creiamo la Repo
Comando per la creazione della repo

```
    npm create vite@latest nomerepo -- --template vue
```
---

### Entriamo nella Repo
Comando per entrare nella repo

```
    code nomerepo
```
---

### Comandi preliminari

```
    npm i
    npm run dev
```

Una volta eseguiti i comandi provare ad entrare nella pagina

---

### Cancellazione file
- Cancellare file `style.css`
- Cancellare riga 2 del file `main.js`, riga contenente l'import del file css
- Cancellare file `HelloWord.vue`
- Svuotare file `App.vue`
- Agiungere boilerplait di vue dentro `App.vue`
- Rimuovo logo Vite nel file `index.html`
- Cambio il title nel file `index.html`
---

### Installiamo SASS 
`npm i sass -D`
- Dentro `assets` creiamo la cartella `scss`
- Dentro `scss` creiamo il file `style.scss`
- All'interno del file `App.vue` nello style mettere `lang="scss"`
- All'interno del tag style importare lo `style.scss` di scss 
```scss
    @use './assets/scss/style.scss';
```
---

### Aggiunta dell'alias per il path (@)
- Importare il path nel file `vite.config.js` `import path from 'path'`
- All'interno della funzione `defineConfig` aggiungiamo l'oggetto `resolve`
```javascript
    resolve: {
        alias: {
            '@': path.resolve(__dirname, 'src')
        }
    }
```
---

### Creare un file `vars.scss` per le variabili in SCSS
- Creiamo il file `vars.scss`
- Importiamo il file `vars.scss` nei file in cui verranno usate le variabili
```scss
    @use 'vars' as *;
```
---

### Importiamo Bootstrap
- `npm i bootstrap`
- Importiamo Bootstrap nel file `main.js`
```javascript
    import 'bootstrap/dist/css/bootstrap.min.css'
```
---

### FontAwesome
1. Installiamo FontAwesome
    ```
        npm i --save @fortawesome/fontawesome-svg-core
    ```
2. Installiamo i tre pacchetti di icone
    ```
        npm i --save @fortawesome/free-solid-svg-icons
        npm i --save @fortawesome/free-regular-svg-icons
        npm i --save @fortawesome/free-brands-svg-icons
    ```
3. Installiamo la libreria
    ```
        npm i --save @fortawesome/vue-fontawesome@latest-3
    ```
4. Importiamo la libreria generica di FontAwesome
    ```javascript
        import { library } from '@fortawesome/fontawesome-svg-core'
    ```
5. Importo il componente di FontAwesome
    ```javascript
        import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
    ```
6. Importo le icone che voglio 
    ```javascript
        import { nomeicone } from '@fortawesome/free-solid-svg-icons'
        import { nomeicone } from '@fortawesome/free-regular-svg-icons'
        import { nomeicone } from '@fortawesome/free-brands-svg-icons'
    ```
7. Inserisco globalmente le icone
    ```javascript
        library.add(nomeicone)
    ```
    Aggiungere un `library.add(nomeicone)` per ogni pacchetto di icone (solid-regular-brands)
8. Rendo le icone disponibili
    ```javascript
        const app = createApp(app);
        app.component('FontAwesomeIcon', FontAwesomeIcon);
        app.mount(#app);
    ```
---

### Fontsource
- Importiamo Fontsource
    ```
        npm i @fontsource/nomedelfontdausare
    ```
- Installiamo Fontsource nel file `main.js`
    ```javascript
        import '@fontsource/nomedelfontdausare'
    ```
- Creare una var con il font installato
- Usare la var nel font-family

---

### Axios
- Istalliamo axios
    ```
        npm i axios
    ```

---

### Aggiungere il README.md
---
# Vue Repository Setup (SASS, Bootstrap, FontAwesome, Fontsource)

### Creating the Repository
Command to create the repository:

```
    npm create vite@latest repository-name -- --template vue
```
---

### Entering the Repository
Command to enter the repository:

```
    code repository-name
```
---

### Preliminary Commands

```
    npm i
    npm run dev
```

Once the commands are executed, try accessing the page.

---

### Deleting Files
- Delete the `style.css` file.
- Remove line 2 from the `main.js` file (the line importing the CSS file).
- Delete the `HelloWord.vue` file.
- Empty the `App.vue` file.
- Add the Vue boilerplate inside `App.vue`.
- Remove the Vite logo from the `index.html` file.
- Change the title in the `index.html` file.
---

### Installing SASS
`npm i sass -D`
- Inside the `assets` folder, create the `scss` folder.
- Inside `scss`, create the `style.scss` file.
- Inside the `App.vue` file, set `lang="scss"` in the `<style>` tag.
- Import the `style.scss` file inside the `<style>` tag:
```scss
    @use './assets/scss/style.scss';
```
---

### Adding an Alias for the Path (@)
- Import the path module in `vite.config.js`:
```javascript
    import path from 'path';
```
- Inside the `defineConfig` function, add the `resolve` object:
```javascript
    resolve: {
        alias: {
            '@': path.resolve(__dirname, 'src')
        }
    }
```
---

### Creating a `vars.scss` File for SCSS Variables
- Create the `vars.scss` file.
- Import the `vars.scss` file where variables are needed:
```scss
    @use 'vars' as *;
```
---

### Importing Bootstrap
- `npm i bootstrap`
- Import Bootstrap in the `main.js` file:
```javascript
    import 'bootstrap/dist/css/bootstrap.min.css';
```
---

### FontAwesome
1. Install FontAwesome:
    ```
        npm i --save @fortawesome/fontawesome-svg-core
    ```
2. Install the three icon packs:
    ```
        npm i --save @fortawesome/free-solid-svg-icons
        npm i --save @fortawesome/free-regular-svg-icons
        npm i --save @fortawesome/free-brands-svg-icons
    ```
3. Install the library:
    ```
        npm i --save @fortawesome/vue-fontawesome@latest-3
    ```
4. Import the FontAwesome library:
    ```javascript
        import { library } from '@fortawesome/fontawesome-svg-core';
    ```
5. Import the FontAwesome component:
    ```javascript
        import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
    ```
6. Import the icons you need:
    ```javascript
        import { iconName } from '@fortawesome/free-solid-svg-icons';
        import { iconName } from '@fortawesome/free-regular-svg-icons';
        import { iconName } from '@fortawesome/free-brands-svg-icons';
    ```
7. Add icons globally:
    ```javascript
        library.add(iconName);
    ```
    Add a `library.add(iconName);` for each icon pack (solid, regular, brands).
8. Make the icons available:
    ```javascript
        const app = createApp(App);
        app.component('FontAwesomeIcon', FontAwesomeIcon);
        app.mount('#app');
    ```
---

### Fontsource
- Install Fontsource:
    ```
        npm i @fontsource/font-name
    ```
- Import Fontsource in the `main.js` file:
    ```javascript
        import '@fontsource/font-name';
    ```
- Create a variable for the installed font.
- Use the variable in the `font-family`.

---

### Axios
- Install Axios:
    ```
        npm i axios
    ```

---

### Adding the README.md
---


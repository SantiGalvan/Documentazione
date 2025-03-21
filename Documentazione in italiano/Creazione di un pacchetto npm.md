# Creazione di un pacchetto

## Descizione

Documentazione su come modificare il `package.json` e il `vite.config.js` e sulla creazione del file `index.js`

## Struttura del Progetto

Prima di iniziare, assicurati di avere una struttura del progetto simile a questa:

```
my-package/
├── src/
│ └── index.js
├── package.json
├── vite.config.js
└── README.md
```

## index.js

Creare un file `index.js` all'interno di `./src`, qui esporteremo i file che ci servono dal pacchetto

```js
    import FileName from './FileName'; // Import del file

    export { FileName } // Export del file da poter usere con il pacchetto
```

## package.json

Nel file `package.json` vanno aggiunte nuove chiavi

```json
{
  "name": "nome-pacchetto",
  "version": "1.0.0",
  "private": false,
  "main": "dist/nome-pacchetto.cjs.js",
  "style": "dist/nome-pacchetto.css",
  "module": "dist/nome-pacchetto.esm.js",
  "exports": {
    ".": {
      "import": "./dist/nome-pacchetto.esm.js",
      "require": "./dist/nome-pacchetto.cjs.js"
    }
  },
  "files": [
    "dist",
    "README.md"
  ],
  "author": "Nome Autore",
  "license": "MIT",
  "description": "Descrizione del pacchetto",
  "scripts": {
    "build": "vite build",
    "prepublishOnly": "npm run build"
  },
  "dependencies": {
    // Dipendenze del progetto
  },
  "devDependencies": {
    "vite": "^3.0.0"
  }
}
```

### Spiegazione delle voci del package.json

- `name`: Il nome del pacchetto.
- `private`: Se impostato su `true`, il pacchetto sarà considerato privato e **non potrà essere pubblicato su npm**. Se è `false` (o omesso), il pacchetto sarà considerato pubblico e potrà essere pubblicato.
- `version`: La versione del pacchetto.
- `main`: Il file principale per il CommonJS (CJS), utilizzato dai moduli che richiedono CommonJS.
- `module`: Il file che contiene il modulo ES (ESM), utilizzato dai moduli che richiedono ES Module.
- `style`: Il file che contiene il CSS per il progetto, utilizzato per la gestione degli stili.
- `exports`: Definisce le modalità di importazione della libreria:
    - `.`: Riferisce il punto di ingresso principale della libreria.
    - `import`: Specifica il file per l'importazione ES Module.
    - `require`: Specifica il file per l'importazione CommonJS.
- `files`: Specifica quali file e cartelle devono essere inclusi nel pacchetto quando viene pubblicato.
    - Include la cartella `dist` che contiene i file di output generati dalla build.
    - Include il file `README.md` per la documentazione del pacchetto.
- `author`: L'autore del pacchetto (da compilare con il nome dell'autore).
- `license`: La licenza del pacchetto (da compilare con il tipo di licenza, ad esempio MIT).
- `description`: Una breve descrizione del pacchetto.
- `scripts`: Comandi npm per eseguire la build e preparare il pacchetto per la pubblicazione.
- `dependencies`: Dipendenze del progetto.
- `devDependencies`: Dipendenze di sviluppo, come Vite.

## vite.config.js

Nel file `vite.config.js` vanno aggiunte le configurazioni per creare un pacchetto

```js
export default defineConfig({
  plugins: [react()],
  build: {
    lib: {
        entry: './src/index.js', // File di ingresso per la libreria
        name: 'nome-libreria', // Nome della libreria
        fileName: (format) => `nome-libreria.${format}.js`, // Creazione file di outpout
        formats: ['esm', 'cjs'] // Formati file di output
      },
      rollupOptions: {
        external: ['react', 'react-dom'], // Dipendenze non incluse nel bundle finale
        output: {
            globals: {
              // Oggetti globali per le librerie esterne
              react: 'React',
              'react-dom': 'ReactDOM',
            }
        }
    }
  }
})
   
```

## Esecuzione della build
Per eseguire la build del pacchetto, esegui il seguente comando:
```bash
npm run build
```
Questo comando genererà i file di output nella cartella `dist`.

## Login su NPM
Prima di pubblicare il pacchetto, devi fare il login su npm. Se non hai un account npm, puoi crearne uno [qui](https://www.npmjs.com/signup).

Esegui il seguente comando per fare il login:
```bash
npm login
```
Ti verrà chiesto di inserire il tuo username, password e email direttamente nel terminale. In alternativa, npm ti fornirà un link in console che potrai aprire nel browser per completare il login tramite la pagina web di npm. Entrambe le opzioni sono valide.

## Pubblicazione del pacchetto
Dopo aver eseguito la build e fatto il login su npm, puoi pubblicare il pacchetto con il seguente comando:
```bash
npm publish
```
Questo comando pubblicherà il pacchetto su npm e sarà disponibile per l'installazione tramite:
```bash
npm install nome-pacchetto
```

## Aggiornamento del pacchetto
Se desideri aggiornare il pacchetto, modifica la versione nel file package.json e ripeti il processo di build e pubblicazione:
```bash
npm version <major|minor|patch>
npm publish
```

## Conclusione
Ora hai creato, configurato, buildato e pubblicato un pacchetto npm. Puoi continuare a migliorare il tuo pacchetto e pubblicare nuove versioni seguendo gli stessi passaggi.


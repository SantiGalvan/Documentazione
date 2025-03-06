# Creazione di un pacchetto

## Descizione

Documentazione su come modificare il `package.json` e il `vite.config.js` e sulla creazione del file `index.js`

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
  // Il file principale per il CommonJS (CJS), utilizzato dai moduli che richiedono CommonJS
  "main": "dist/project-name.cjs.js",

  // Il file che contiene il CSS per il progetto, utilizzato per la gestione degli stili
  "style": "dist/project-name.css",

  // Il file che contiene il modulo ES (ESM), utilizzato dai moduli che richiedono ES Module
  "module": "dist/project-name.esm.js",

  // Definizione delle modalità di importazione della libreria
  "exports": {
    ".": {
      // Quando si importa il pacchetto in modalità ES (importazione statica), si fa riferimento al file ESM
      "import": "./dist/project-name.esm.js",

      // Quando si importa il pacchetto in modalità CommonJS (require), si fa riferimento al file CJS
      "require": "./dist/project-name.cjs.js"
    }
  },

  // Specifica quali file e cartelle devono essere inclusi nel pacchetto quando viene pubblicato
  "files": [
    // Includi la cartella 'dist' che contiene i file di output generati dalla build
    "dist",
    // Includi il file README.md per la documentazione del pacchetto
    "README.md"
  ],

  // L'autore del pacchetto (attualmente vuoto, ma può essere compilato con il nome dell'autore)
  "author": "",

  // La licenza del pacchetto (da compilare con il tipo di licenza, ad esempio MIT)
  "license": "",

  // Una breve descrizione del pacchetto
  "description": ""
}
```

## vite.config.js

Nel file `vite.config.js` vanno aggiunte le configurazioni per creare un pacchetto

```js
    build: {
      lib: {
      entry: './src/index.js', // File di ingresso per la libreria
      name: 'nome-libreria', // Nome della libreria
      fileName: (format) => `nome-libreria.${format}.js`, // Creazione file di outpout
      formats: ['esm', 'cjs'] // Formati file di output
      },
      rollupOptions: {
      external: ['react', 'react-dom', 'thecore-auth'], // Dipendenze non incluse nel bundle finale
      output: {
          globals: {
              // Oggetti globali per le librerie esterne
              react: 'React',
              'react-dom': 'ReactDOM',
              'thecore-auth': 'thecore-auth'
          }
      }
    }
  }
   
```

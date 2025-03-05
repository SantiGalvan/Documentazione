# Comandi console Vue.js:

### Come creare un progetto vite-view:

`npm create vite@latest nome-progetto -- --template vue `

### Installazione generale pacchetti:

`npm i `

### Avvio server:

`npm run dev `

### Come installare sass:

`npm i –D sass `

### Come installare axios:

`npm i axios `

### Come installare Bootstrap:

`npm i bootstrap` -> importare bootstrap nel main.js ->(vedere sotto)

```javascript
import "bootstrap/dist/css/bootstrap.min.css";

// In caso che hai scss mettere anche
("bootstrap/dist/scss/bootstrap.min.scss");
```

### Come installare FontAwesome:

`npm i --save @fortawesome/fontawesome-svg-core`

`npm i --save @fortawesome/free-solid-svg-icons`  
`npm i --save @fortawesome/free-regular-svg-icons`  
`npm i --save @fortawesome/free-brands-svg-icons`  
(ultime 3 righe in base alle icone che vuoi)

`npm i --save @fortawesome/vue-fontawesome@latest-3`

```javascript
import { library } from "@fortawesome/fontawesome-svg-core";
import { FaUser as EsempioFaUser } from "@fortawesome/free-solid-svg-icons";
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";

library.add(EsempioFaUser);

// Tra createApp e mount
app.component("FontAwesomeIcon", FontAwesomeIcon);
```

### Come installare il router di vue:

`npm i vue-router@4 `

<div style="margin-top: 70px;"></div>
 
# Comandi console Laravel:

### Installare Laravel:

`composer create-project laravel/laravel:^10 nome-progetto`  
(numero = versione laravel)

### Installazione dipendenze generali:

`composer i`

### Installazione librerie desiderate:

`composer require NomeLibreria`

### Come avviare un server su laravel:

`php artisan serve OPPURE php –s localhost:8000 –t public`  
`npm run dev`

### Come togliere tailwind e aggiungere bootstrap:

`composer require pacificdev/laravel_9_preset`  
`php artisan preset:ui bootstrap`  
`npm i`  
rimuovere riga di codice (type:’module’ riga 3) nel package.json  
aggiungere nel file app.scss

```javascript
@import '~bootstrap/scss/bootstrap'

// Aggiungere nell’oggetto input in app.js
'resources/scss/app.scss', 'resources/js/app.js',

// Nel layout generale aggiungere nella head
@vite(['resources/js/app.js'])
```

`npm run dev`

### Come creare un modello:

`php artisan make:model NomeTabellAlSingolare `
se vuoi aggiungere una di queste opzioni aggiungi alla fine -rmsf indicando
quale vuoi con le lettere:

- r = resouce
- m = migration
- s = seeder
- f = factory

### Come fare una migrazione:

`php artisan make:migration create_Esempio_table `

### Come comunicare con il db:

`php artisan migrate`  
questo comando legge le migrations e crea il db se non lo hai

### Come fare il refresh del db:

`php artisan migrate:refresh`  
se si vuole fare il seed con il refresh aggiungere `--seed` alla fine

### Come fare il rollback del db:

`php artisan migrate:rollback `

### Come fare il reset del db:

`php artisan migrate:reset `

### Come fare un seeder:

`php artisan make:seeder NomeDelModelloSeeder`  
se vuoi importare direttamente il modello nel seeder aggiungi alla fine:  
`--model=NomeModello`  
chiamare il seeder sul `DatabaseSeeder`

### Come fare il seed:

`php artisan db:seed `

### Come creare una factory:

`php artisan make:factory NomeModelloFactory`
se vuoi importare direttamente il modello nella factory aggiungi alla fine:  
`--model=NomeModello `

### Come creare un controller:

`php artisan make:controller NomeModelloController`
se vuoi avere un controller preinpostato per le risorse aggiungi alla fine `-r`  
r = resouce

### Come installare laravel breeze (Laravel con autenticazione):

`composer require laravel/breeze --dev`  
`php artisan breeze:install`  
`composer require pacificdev/laravel_9_preset` (non cambiare il 9)  
`php artisan preset:ui bootstrap –auth`  
`npm i`  
`npm run dev`

### Come creare le view:

`php artisan make:view NomePagina`  
se vuoi creare anche una cartella con questo comando scrivi anche il nome della cartella all’inizio seguito dal punto e il nome della pagina

### Come creare le view per le crud con un comando:

`composer require lanciweb/laravel-make-view`  
`php artisan make:view NomeModello --crud`

### Come fare il link allo storage (per poter usare l’asset):

mettere `FILESYSTEM_DISK = public`  
mettere nel filesystems.php a riga 16

```php
 'default' => env('FILESYSTEM_DISK', 'public')
```

`php artisan storage:link`

### Come creare il controller API:

`php artisan make:controller Api/NomeModelloController --api`  
`--model=NomeModello`

### Come controllare tutte le rotte che si hanno creato:

`php artisan route:list`  
si possono filtrare aggiungendo `--path=api`

### Come creare una mail:

`php artisan make:mail NomeCheVuoiMail`  
`php artisan make:view mails.contacts.message`

---

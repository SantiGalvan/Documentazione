# Comandi clonazione Repo Laravel

## Asset di Front
```
    npm i
```

## Asset di Back
```
    composer install
```

## Creare file .env
```
    cp .env.example .env
```

## Generare l'app-key
```
    php artisan key:generate
```

## Configura i dati di connessione al DB
```
    DB_CONNECTION=mysql
    DB_HOST=127.0.0.1
    DB_PORT=3306
    DB_DATABASE=nome_del_tuo_database
    DB_USERNAME=tuo_username
    DB_PASSWORD=tua_password
```

## Migrare il DB 
```
    php artisan migrate
```

## Lanciare il server back
```
    php artisan serve
```
- Se non ti vanno le immagini usare questo comando
```
    php -S localhost:8000 -t public
```

## Lanciare server Front
```
    npm run dev
```
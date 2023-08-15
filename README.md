# sail

Jalankan berikut di directory source untuk install package composer (jika baru saja git clone, blm ada directory vendor)

```shell
docker run --rm \
    -u "$(id -u):$(id -g)" \
    -v $(pwd):/var/www/html \
    -w /var/www/html \
    laravelsail/php81-composer:latest \
    composer install --ignore-platform-reqs
```

buka file ~/.bashrc, tambahkan line berikut di paling bawah (restart komputer setelah itu):

```shell
alias sail='[ -f sail ] && bash sail || bash vendor/bin/sail'
```

jalankan sail up utk create container

```shell
sail up -d
```

```shell
sail npm install

sail artisan key:generate
sail artisan storage:link

sail npm run dev // for development
sail npm run build // for production

```

Nama server host db akan sama dengan jenis db yg di set di docker. di .env, pastikan DB_HOST diganti sesuai dgn db yg diset di docker, mariadb ato mysql. user password akan sesuai .env. pwd root dan user disamakan otomatis (sesuai docker)

```shell
DB_HOST=mariadb
```

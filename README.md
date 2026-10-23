# docker-php-5.6.40-alpine3.8-php2shell-patch

Salvaged PHP 5.6.40 Dockerfiles from the original `php` images, with the
php2shell (CVE-2026-109618, CVE-2026-109619) patches applied from
[Anton-Barinov/php2shell-patches](https://github.com/Anton-Barinov/php2shell-patches).

## Usage

```
ghcr.io/arisudesu/php:5.6.40-cli-alpine3.8-php2shell-patch
ghcr.io/arisudesu/php:5.6.40-fpm-alpine3.8-php2shell-patch
ghcr.io/arisudesu/php:5.6.40-zts-alpine3.8-php2shell-patch
```

To build and publish them:

```sh
docker compose build
docker compose push
```

The patch ships in `/usr/src/php-patches/` inside the image and is applied by
`docker-php-source extract`, which means `docker-php-ext-install` and any
derived image that rebuilds from source get patched sources as well.

## Credits

- [docker-library/php](https://github.com/docker-library/php) — the original
  Dockerfiles and `docker-php-*` helper scripts.
- [Anton-Barinov/php2shell-patches](https://github.com/Anton-Barinov/php2shell-patches)
  — the php2shell patches.

# Headless Wordpress

A WordPress backend serving up content via the [WP REST API](https://developer.wordpress.org/rest-api/)

The Wordpress Backend includes:

- **An installer script which bootstraps a core WordPress installation:** This script installs MySQL and WordPress locally in [Docker](https://www.docker.com/) containers.
- **WordPress plugins you need to set up custom post types and custom fields** ([Advanced Custom Fields](https://www.advancedcustomfields.com/) and [Custom Post Type UI](https://wordpress.org/plugins/custom-post-type-ui/)).
- **WordPress Plugins which expose those custom fields and WordPress menus** in the [WP REST API](https://developer.wordpress.org/rest-api/) ([ACF to WP API](https://wordpress.org/plugins/acf-to-wp-api/) and [WP-REST-API V2 Menus](https://wordpress.org/plugins/wp-rest-api-v2-menus/)).

## Installing

_Prerequisite:_ Before you begin, you need [Docker](https://www.docker.com) installed. On Linux, you might need to install [docker-compose](https://docs.docker.com/compose/install/#install-compose) separately.

Docker Compose builds and starts two containers by default: `publicsite-db`, `publicsite-wp`:

```
cd WP-Backend
docker-compose up -d
```

**Wait a few minutes** for Docker to build the services for the first time. After the initial build, startup should only take a few seconds.

You can use some useful Docker tools like Kitematic and/or VSCode Docker plugin to follow logs, start / stop / remove containers and images.

With the containers running:

The `publicsite-wp` container exposes Apache on host port `8080`:

- Dashboard: [http://localhost:8080/wp-admin](http://localhost:8080/wp-admin) (default credentials `thomasmuller`/`bayernMunich`)
- REST API: [http://localhost:8080/wp-json](http://localhost:8080/wp-json)

#### Database

The `publicsite-db` container exposes MySQL on host port `3307`.

## Acknowledgments

Thanks to Postlight for their [WordPress + React Starter Kit](https://github.com/postlight/headless-wp-starter)

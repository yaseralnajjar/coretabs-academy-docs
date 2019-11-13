# Discourse

## Assumption

These configurations assume that discourse is configured to work with the specified port in `/etc/nginx/sites-enabled/default` file.

##  Editing the `app.yml` file

```text
cd /var/discourse/
vim containers/app.yml
```

##  Enabling SSO

This tutorial says it all: [https://meta.discourse.org/t/official-single-sign-on-for-discourse-sso/13045](https://meta.discourse.org/t/official-single-sign-on-for-discourse-sso/13045)

##  Enabling CORS

Just add the var `DISCOURSE_ENABLE_CORS` and set it to true

```text
env:
  LANG: en_US.UTF-8
  # DISCOURSE_DEFAULT_LOCALE: en

  ## How many concurrent web requests are supported? Depends on memory and CPU cores.
  ## will be set automatically by bootstrap based on detected CPUs, or you can override
  UNICORN_WORKERS: 4

  ## TODO: The domain name this Discourse instance will respond to
  ## Required. Discourse will not work with a bare IP number.
  DISCOURSE_HOSTNAME: discourse.coretabs.net

  DISCOURSE_ENABLE_CORS: true
```

##  Changing discourse exposed ports

Adding this part to your `app.yml` file would change the exposed ports from `80, 443` into `4000, 4001`

```text
expose:
  - "4000:80"   # http
  - "4001:443" # https
```

Your `app.yml` file should look like:

```text
## this is the all-in-one, standalone Discourse Docker container template

templates:
  - "templates/postgres.template.yml"
  - "templates/redis.template.yml"
  - "templates/web.template.yml"
  - "templates/web.ratelimited.template.yml"

## which TCP/IP ports should this container expose?
## If you want Discourse to share a port with another webserver like Apache or nginx,
## see https://meta.discourse.org/t/17247 for details
expose:
  - "4000:80"   # http
  - "4001:443" # https

params:
  ...
```

##  Rebuilding discourse

```text
./launcher rebuild app
```


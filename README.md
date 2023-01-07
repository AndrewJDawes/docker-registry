# docker-registry

## Behind NGINX proxy

You're going to want to make sure you have these directives set:

```
# disable any limits to avoid HTTP 413 for large image uploads
client_max_body_size 0;

# required to avoid HTTP 411: see Issue #1486 (https://github.com/moby/moby/issues/1486)
chunked_transfer_encoding on;
```

Other helpful NGINX directives can be found in the [Docker Recipe](https://docs.docker.com/registry/recipes/nginx/)
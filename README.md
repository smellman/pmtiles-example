# pmtiles-example

[PMTiles](https://github.com/protomaps/PMTiles) example with OpenMapTiles planet.

original code: https://protomaps.github.io/protomaps-themes/examples/maplibre-basemap.html

## cors settings in nginx

```
  location /static {
    alias /srv/static;
    autoindex on;
    autoindex_exact_size off;
    autoindex_localtime on;

    add_header 'Access-Control-Allow-Origin' "$http_origin" always;
    add_header 'Access-Control-Allow-Credentials' 'true' always;
    add_header 'Access-Control-Allow-Methods' 'GET, POST, PUT, DELETE, OPTIONS' always;
    add_header 'Access-Control-Allow-Headers' 'Accept,Authorization,Cache-Control,Content-Type,DNT,If-Modified-Since,Keep-Alive,Origin,Range,User-Agent,X-Requested-With' always;

    if ($request_method = 'OPTIONS') {
      # Tell client that this pre-flight info is valid for 20 days
      add_header 'Access-Control-Allow-Origin' "$http_origin" always;
      add_header 'Access-Control-Allow-Headers' 'Accept,Authorization,Cache-Control,Content-Type,DNT,If-Modified-Since,Keep-Alive,Origin,Range,User-Agent,X-Requested-With' always;
      add_header 'Access-Control-Max-Age' 1728000;
      add_header 'Content-Type' 'text/plain charset=UTF-8';
      add_header 'Content-Length' 0;
      return 204;
    }
  }
```

# Proxy traefik : usage actuel, implémentations et configurations

## Commandes pêle-mêle
### renouvellement de certificat avec certbot sans automatisation traefik
```shell
$ sudo tee /usr/local/bin/renew-certificates >/dev/null <<'EOF'
#!/bin/sh
docker run --rm -p 80:80 \
  -v /etc/letsencrypt:/etc/letsencrypt \
  -v /var/lib/letsencrypt:/var/lib/letsencrypt \
  certbot/certbot renew "$@"
EOF
```

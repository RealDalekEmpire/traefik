# traefik



labels:
      - "traefik.enable=true"
      - "traefik.http.routers.linkwarden.entrypoints=http"
      - "traefik.http.routers.linkwarden.rule=Host(`links.lawsoncorp.net`)"
      - "traefik.http.middlewares.linkwarden-https-redirect.redirectscheme.scheme=https"
      - "traefik.http.routers.linkwarden-secure.entrypoints=https"
      - "traefik.http.routers.linkwarden-secure.rule=Host(`links.lawsoncorp.net`)"
      - "traefik.http.routers.linkwarden-secure.tls=true"
      - "traefik.http.routers.linkwarden-secure.service=linkwarden"
      - "traefik.http.services.linkwarden.loadbalancer.server.port=3000"
      - "traefik.docker.network=proxy"


networks:
  internal:
  proxy:
    external: true # or comment this line to auto create the network

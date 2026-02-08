Same as main except it includes the Traefik commands to redirect to the /admin page and uses http://pihole.cmcc-gaza.lan as the URL
    labels:
      - "traefik.enable=true"
      - "traefik.http.middlewares.pihole-redirect.redirectregex.regex=^http://pihole.cmcc-gaza.lan/$$"
      - "traefik.http.middlewares.pihole-redirect.redirectregex.replacement=http://pihole.cmcc-gaza.lan/admin/"
      - "traefik.http.routers.pihole.middlewares=pihole-redirect"

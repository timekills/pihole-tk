Same as main except it includes the Traefik commands to redirect to the /admin page and uses 
the Coolio LAN URL of http://pihole.192.168.10.226.sslip.io

    labels:
      - "traefik.enable=true"
      - "traefik.http.middlewares.pihole-redirect.redirectregex.regex=^http://pihole.192.168.10.226.sslip.io/$$"
      - "traefik.http.middlewares.pihole-redirect.redirectregex.replacement=http://pihole.192.168.10.226.sslip.io/admin/"
      - "traefik.http.routers.pihole.middlewares=pihole-redirect"

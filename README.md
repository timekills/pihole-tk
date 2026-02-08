Uses the "coolify" network and only ports 53 (UDP and TCP) to allow
Coolify's reverse proxy (Traefik) to be master.

No SSL (443) access, http only for LAN access.

Does *not* employ Traefik labels, so you must add /admin to the URL/IP
when accessing the web GUI of PiHole.

*NOTE* Requires editing of .env file to include the WEBPASSWORD and COOL_IP
(Coolio's local or Docker IP)

---also note the WEBPASSWORD is not actually honored upon creation;
the PiHole install creates it's own random password and overwrites
the user created one, so you'll have to check the Docker logs to
get the randomly created password for first logon.

      WEBPASSWORD: "${WEBPASSWORD}"
      DNSMASQ_LISTENING: "all"
      FTLCONF_local_ipv4: "${COOL_IP}"
      ServerIP: "${COOL_IP}"

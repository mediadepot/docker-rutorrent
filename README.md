Based on `linuxserver/rutorrent`

# Requirements


# Environmental
The following environmental variables must be populated, when running container

- PUID,
- PGID

# Ports
The following ports must be mapped, when running container

 - 80 #webui listen
 - 5000 #rtorrent XMLRPC port.
 - 51413 #bittorrent
 - 6881 #bittorrent

# Volumes
The following volumes must be mapped, when running container

- /config
- /blackhole
- /processing
- /downloads

The following subfolders should exist in the above mapped volumes:

- tvshows
- movies
- music
- any other folders that you

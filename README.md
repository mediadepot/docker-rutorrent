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

# References
 - https://plaza.quickbox.io/t/rutorrent-ratio-groups/449
 - https://github.com/rakshasa/rtorrent/wiki/RTorrentRatioHandling


# TODO list
- [x] catchall watch folder (/blackhole/*.torrent) should work correctly and download to "unsorted"
- [x] dynamic watch directories
	- [x] remove the torrent from the watch directory once its loaded using AutoTools plugin
	- [x] auto-start watch directory torrents
- [x] download all torrents to /processing directory
- [?] redirect rtorrent daemon logs to STDOUT
- [x] move completed downloads into dynamic `/downloads` subdirectories using AutoTools
- [ ] DEPOT default user/password authentication for webui
- [-] [scheduling/QoS](http://rtorrent-docs.readthedocs.io/en/latest/use-cases.html#scheduled-bandwidth-shaping)
- [ ] Auto cleanup? Completed torrents that are stopped and older than 2 months?
- [x] [stop seeding when download is complete](https://github.com/rakshasa/rtorrent/wiki/Common-Tasks-in-rTorrent#move-completed-torrents-to-a-fixed-location)
- [ ] [Performance tuning](https://github.com/rakshasa/rtorrent/wiki/Performance-Tuning)
- [ ] logrotate
- [ ] [better logging. ](https://serverfault.com/questions/599103/make-a-docker-application-write-to-stdout)
- [x] ensure that deleting a partially downloaded/inprogress torrent will actually delete the associated data
	- [ ] when deleting a torrent we should always delete the .torrent file too
	- [ ] when deleting a torrent, sometimes the download directory is not deleted.
- [ ] pushover support
- [ ] custom themes

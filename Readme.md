# Useful commands for administering of IBM(R) Lotus Domino server

## User sessions

### Block user sessions, light mode
- New user connections are not permitted until the server is rebooted
- Existing user connections are allowed

```set config server_restricted=1```

### Block user sessions, strict mode
- New user connections are not permitted even after rebooting the server
- Existing user connections are allowed

```set config server_restricted=2```

### Allow user sessions
```set config server_restricted=0```

## Flush database cache
```dbcache flush```

## Installation check-list
- Install distributive
- Do not restart server
- move ```cert.id``` from ```data``` folder, backup it
- set up ```notes.ini```:
    - ```servertask=``` — run task after every reboot
    - ```servertaskat1=``` — run task in 01:00 hour daily

## Quick reinstallation hints (without uninistall/install distributive):
- save file ```notes.ini```
- delete files and folders:
    - ```data\names.nsf```
    - ```data\desktop8.ndk```
    - ```data\cache.ndk```
    - ```data\bookmark.nsf```
    - ```data\mail.box```
    - ```data\log.nsf```
    - ```data\busytime.nsf```
    - ```data\IBM_TECHNICAL_SUPPORT\```
    - ```data\user.id```
    - ```data\DAOS\```

## Limitations
- Database is limited to 64 Gigabytes (68719476736 bytes)
- Organization name 3-64 symbols
- Server name up to 79 symbols
- Notes network up to 31 symbols

## Domino console
- command is limited to 255 symbols
- commands are case insensitive, but parameters might be
- warnings:
    - when one is typing command, it can be mixed with server's messages
    - pressing ```Pause``` keyboard button can stop some server tasks

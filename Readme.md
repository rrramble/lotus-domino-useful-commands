# Useful commands for administering of IBM(R) Lotus Domino server

## Disclaimer
The text was taken from own handwritten self-taught notes and translated to English. Therefore, there might be unintended errors and usage of non-official terms.

## User sessions

### Block user sessions, light mode
- New user sessions are not permitted until the server is rebooted
- Existing user sessions are allowed

```set config server_restricted=1```

### Block user sessions, strict mode
- New user sessions are not permitted even after rebooting the server
- Existing user sessions are allowed

```set config server_restricted=2```

### Drop user sessions
```drop all```

### Allow user sessions
```set config server_restricted=0```

## Flush database cache
```dbcache flush```

## Installation check-list
- For reinstallation:
    - prepare existing files: ```cert.id```, ```admin.id```, ```server.id```
    - know ```Lotus server name```, ```Lotus domain name```, ```Fully qualified name```
- Install distributive, install FP files (upgrades)
- Do not restart server
- Run 'Lotus Domino Server' and make initial setup
- Run 'Lotus Domino Server', choose 'Start Domino as a regular application'
- Allow connections in Firewall warning
- Move ```cert.id``` from ```data``` folder, backup it
- Set up ```notes.ini```:
    - ```servertask=``` — run task after every reboot
    - ```servertaskat1=``` — run task in 01:00 hour daily

## Quick reinstallation hints (without uninistall/install distributive):
- backup file ```notes.ini```
- delete files and folders:
    - ```data\bookmark.nsf```
    - ```data\busytime.nsf```
    - ```data\cache.ndk```
    - ```data\desktop8.ndk```
    - ```data\log.nsf```
    - ```data\mail.box```
    - ```data\names.nsf```
    - ```data\user.id```
    - ```data\IBM_TECHNICAL_SUPPORT\```
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

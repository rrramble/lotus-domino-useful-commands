# Useful commands for administering of IBM(R) Lotus Domino server

## User sessions

### Block user sessions light
- New user connections are not permitted until the server is rebooted
- Existing user connections are allowed

```set config server_restricted=1```

### Block user sessions strict
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
-- ```servertask=``` — run task after every reboot
-- ```servertaskat1=``` — run task in 01:00 hour daily

## Reinstalling hints:
- save ```notes.ini```
- delete files:
    - ```data\names.nsf```
    - ```data\desktop8.ndk```
    - ```data\cache.ndk```
    - ```data\bookmark.nsf```
    - ```data\mailbox```
    - ```data\log.nsf```
    - ```data\busytime.nsf```
    - ```data\ibm_technical_support```
    - ```data\user.id```
    - ```DAOS\```

# Limits
- Database is limited to 64 Gigabytes (68719476736 bytes)
- Organization name 3-64 symbols
- Server name 79 symbols
- Notes network 31 symbols

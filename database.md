# Database operations

## Creating
Database are \*.nsf files and created based on a template file with extension \.ntf.

From Lotus Domino menu: ```File > Application > New```.

Required fields:
- server: ```SERVER_NAME/COMPANY_NAME/COUNTRY_CODE```
- template: ```CHOOSE_TEMPLATE```
- title
- filename: specify NSF file name
- encryption (for example ```do not locally encrypt```)

## Access control lists (ACL)

### User roles
- ```depositor```: can create documents; can not read documents, even created by them
- ```reader```: can read documents:
  - if document explicitly set this user as reader
  - if document does not have ```reader``` field
- ```author```: has all rights as ```reader```, can edit documents wich have this user set as ```author```.
  - A Document can have several ```reader``` and ```author``` fields.
  - If a document does not have the ```reader``` field, or it is empty, then the document can be reached any user with ```reader``` or higher premission.
- ```editor```: as ```author```, plus can edit documents, which are read-only
- ```designer```: as ```editor```, plus can change design of the Database
- ```manager```: as ```designer```, plus can change access to the Database

> Some tasks such as ```move``` or ```create replica``` executed not immidietly, but according to ```Administrative process```.

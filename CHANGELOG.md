Build 21
==
(2016.12.18)
- Added ugly button to force bow to update all info
- DB refactoring finished
  - db.tag : deleted, created alias, added precreation of non-existed buckets for new tag
  - db.catalog : the same as for db.tag
- QURL refactoring finished
  - Fixed isues where bow was not able to make bearer auth reqest for HEAD/DELET/headers requests
  - Nice & compact method capable to serv all reqest
- Fix: error when registry storage was changed externally
- Fix: random order of repos/names/tags
- Fix: error for non-existing catalogs just after creation
- Fix: db.upgrade for the most old versions

Build 20
==
(2016.12.04)
- Added possibility to login through bearer token
- Added explicit secure/insecure checkbox in repo config
- DB schema redesign
  - add '_info' bucket to store confings, move configs into it and create upgrade way
  - from 'repo.go' to general 'db' middleware
  - add db versions, check it in each restart, do upgrade if needed
- Splitted 'db' => 'put', 'get', 'delete', 'schema', 'upgrade' and 'alias'
- Splitted main.go => package 'handler' + package 'main'
- Added full test env (auth server, basic auth registry and token based auth) + gitignore
- Fixed error in blob size conversion

Build 19
==
(2016.11.01)  
- API compatibility covered by tests  
- Fixed time conversion bug for Manifest Daemon
- Upgrade moved from db to utils
- Size conversion moved from db to utils
- MakeQueryToRepo now operate with http status codes

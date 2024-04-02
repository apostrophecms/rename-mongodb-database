# rename-mongodb-database
<a href="https://apostrophecms.com/"><img src="https://raw.githubusercontent.com/apostrophecms/rename-mongodb-database/main/logos/logo-box-madefor.png" align="right" /></a>

Rename a mongodb database with one command:

```bash
# Talks to mongodb on localhost by default
rename-mongodb-database oldname newname

# Talk to some other mongodb installation (all MongoDB URIs work)
rename-mongodb-database oldname newname --uri=mongodb://user:pass@somewhere

# Rename many databases with a matching prefix at once
# renames oldprefix-db1 to newprefix-db1, oldprefix-db2 to newprefix-db2, etc.
# does not rename someotherprefix-db
rename-mongodb-database oldprefix newprefix --many
```

This command will overwrite the new database with the contents of the old, if it already exists, and drop the old database.

## Installation

```
npm install -g @apostrophecms/rename-mongodb-database
```

## Requirements

**You must have `mongodump` and `mongorestore` installed.** Depending on how you installed MongoDB itself, this might not be automatic.
See the MongoDB documentation for more information about the MongoDB command line tools.

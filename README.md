# rename-mongodb-database

Rename a mongodb database with one command:

```bash
# Talks to mongodb on localhost by default
rename-mongodb-database oldname newname

# Talk to some other mongodb installation
rename-mongodb-database oldname newname --uri=mongodb://user:pass@somewhere.com

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

**You must have `mongodump`, `mongosh` (or `mongo`) and `mongorestore` installed.** Depending on how you installed MongoDB itself, this might not be automatic.
See the MongoDB documentation for more information about the MongoDB command line tools.

**You must have at least MongoDB 3.4,** but note that MongoDB 5.0 is the oldest supported release anyway, so upgrading is recommended.

Very old versions of the command line tools that do not support `--archive` will not work.

## Note on MongoDB URLs

If your MongoDB URL is not technically a valid URL, this tool will not be able to parse it. You should be fine with
Atlas `mongodb+srv//` URLs and regular `mongodb://` URLs.
# The Key MongoDB Characteristics (and how they differ from SQL Databases)

MongoDB is diff from SQL. It is a NoSQL approach with opposite philosphy to that of normal SQL. No structured normalized data.

## BSON Data Structure

No Schema
* Things can be missing
  * User can be missing an age
* Dev responsiblity to work with clean day even if the DB has dirty data

## Relations

* No / Few Relations!
* Relational Data needs to be merged manually (kind of manually at least...)
* Mongo will search for data and won't do any merging most of the time.
* NoSQL is good for heavy READWRITE applications
* Performance and flexibility

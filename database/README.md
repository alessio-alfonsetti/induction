# United Nations Global Induction Platform

## Data Migration

parse.com provides a one click tool to export the data into a database which is accessable through:

`mongodb://<dbuser>:<dbpassword>@<ip or url>:<port>/induction`

This means the destination database needs to be exposed to outside world. If this is not an option, another way is exporting the data into a free database created at mlab.com, and from mlab, exporting the data into a local folder using:

```
mongodump -h <mlab url of the database>:<mlab port of the database> -d induction -u <user> -p <password> -o <output directory>

```

This is how the data in "induction" folder is obtained. To import the data in the "induction" folder into OICT hosted database, use:

```
mongorestore -h <your db url or ip>:<your db port> -d induction -u <user> -p <password> <input db directory>

```

Example:

`mongorestore -h localhost:27017 -d induction -u john -p Doe123456 induction`

 
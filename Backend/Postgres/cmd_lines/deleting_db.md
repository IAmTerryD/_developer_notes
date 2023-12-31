# Deleting Database

To delete a PostgreSQL database, you need to use the DROP DATABASE SQL command. 

Here are the steps to delete a PostgreSQL database:

## Connect to PostgreSQL 

```
psql -U your_username -d your_database
```

```
psql -U postgres -d postgres
```

## Connect to a DB you don't want to delete

```
\c postgres
```

## Execute the DROP DATABASE Command:

Once connected, run the following SQL command to delete the database:

```
DROP DATABASE database_name;
```

```
DROP DATABASE ehr;
```

## Creating Database:

```
CREATE DATABASE ehr;
```

## Error Cannot Drop Database Your Connected On

Create a new Test database. Connect to that using step 1, then follow step 2. 

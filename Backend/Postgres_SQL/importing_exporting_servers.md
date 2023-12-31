# Go to .bin location

> C:\Program Files\PostgreSQL\16\bin

Open terminal and type:

```
.\pg_dump -U postgres -h localhost -d postgres -F c -f C:\Users\Terence\Desktop\mydatabase_backup.dump
```

# To Import Database

```
pg_restore -d your_database_name -U your_username -h your_host -p your_port -W -v your_dump_file.dump

# Copy Below 

.\pg_restore -d postgres -U postgres -h localhost -p 5432 -W -v C:\Users\teren\Desktop\mydatabase_backup.dump

pg_restore -d postgres -U postgres -h localhost -p 5432 -W -v C:\Users\teren\Desktop\mydatabase_backup.dump
```
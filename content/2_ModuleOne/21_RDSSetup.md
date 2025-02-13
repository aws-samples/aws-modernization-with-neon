---
title: "Connecting to your RDS Database"
chapter: true
weight: 21
---
# Accessing and Managing Your RDS Database  
This guide will walk you through accessing your PostgreSQL database, getting the connection details needed for the Neon setup, and seeding the database with sample data.  
---
## 🔑 Getting Your Database Connection Details  
Before connecting to the database, you'll need to get your connection details. These are stored as environment variables.  
💡 **Pro Tip**: Copy these values somewhere safe - you'll need them later!  
1. Open a new terminal in **VSCode Server**.  
2. Run these commands to view your connection details in your VSCode Terminal:  
```bash
echo $DB_ENDPOINT     # Shows your database endpoint  
echo $DB_USERNAME     # Shows your database username  
echo $DB_PASSWORD     # Shows your database password  
echo $DB_NAME         # Shows your database name  
echo $DATABASE_URL    # Shows the full connection string
```
![Screenshot of Environment Variable Output](/images/environment-variables-output.png)  

---

## 🔄 Seeding the Database  

Once you have confirmed your database connection details, follow these steps to seed the database with sample data:  

1. Decompress and load the dataset into the database:  

```bash
echo "Decompressing dataset..."  
pg_restore -O -U $DB_USERNAME -d $DB_NAME -h $DB_ENDPOINT /tmp/employees.sql.gz  
echo "Dataset decompressed"  
```

![Screenshot of Dataset Decompression](/images/decompress-dataset.png)  

2. Set up schema access for easier database usage:  

```sql
echo "Setting up schema access..."  
psql -h $DB_ENDPOINT -U $DB_USERNAME -d $DB_NAME
echo "Schema access setup complete" 
```

Set search path for easier access  
```sql
ALTER DATABASE employees SET search_path TO employees, public;  
```

![Screenshot of Schema Setup](/images/schema-setup.png)  

3. Enter the following command while connected to the database to set the current session's search path:  

```sql
-- Set current session's search path  
SET search_path TO employees, public;  
```

## 🔍 Exploring the Database  

Once the dataset is loaded, you can explore it using these commands:  

- List all Schemas and tables:  

```sql
\d
```

![Screenshot of List Tables Output](/images/list-tables-output.png)
**Note**: You may have to exit (Enter: \q) and reenter the Database if no relations are found initially.

- View detailed table information for the `employee` table:  

```sql
\d+ employee
```

![Screenshot of Table Information](/images/table-info.png)  

- Run a sample query:  

```sql
SELECT COUNT(*) FROM department;
```

![Screenshot of Sample Query Output](/images/sample-query-output.png)  

Exit the database:

```sql
\q
```

---

## 🔧 Troubleshooting  

Can't see your environment variables? Try these steps:  

1. Close and reopen your terminal.  


2. Check if the variables are in `/etc/environment`:  

```bash
cat /etc/environment  
```

3. Source the environment file:  

```bash
source /etc/environment  
```

🛑 **Database Issues**: If you're having trouble connecting to the database or the `employees` data isn't loading properly, run:  

```bash
sudo /usr/local/bin/setup_db.sh  
```

This script will reload the sample database and set up all necessary configurations.  

⚠️ **Security Note**: Keep your database credentials secure and never share them with others!  

---

🎯 **Next Steps**: Once you have your connection details and the database is seeded, proceed to the Neon setup section.

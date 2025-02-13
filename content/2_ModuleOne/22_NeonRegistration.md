---
title: "Neon Registration"
chapter: true
weight: 23
---

### 1. Create a Neon account

If you’re new to Neon, the first step is to [sign up](https://console.neon.tech/signup) and create your initial project in Neon using the steps detailed in the section below.

### 2. Create a Neon database 

**Make sure your Neon database is deployed to the same AWS region as your RDS database (us-west-2).**

After you have signed up for a Neon account, follow our [getting started guide](https://neon.tech/docs/get-started-with-neon/signing-up) to create your initial project

![Neon Project Creation](/images/neon-project-creation.png)

You will be introduced to these key Neon terms:

![Neon Object Hierarchy](/images/Neondatabasedr.png)

- **Project:** The top-level container for your Neon databases—the logical equivalent to an “instance” in RDS.
- **Branch:** A versioned copy of your database environment. Each Neon project can have multiple branches, as we will see later.
- **Database:** The actual database instance where your data resides. In Neon, databases live inside branches.

Neon is built on an innovative [branch-based architecture](https://neon.tech/docs/introduction/branching):

- The **main branch** will be your **primary development branch**, where you’ll load the data from your RDS database every night.
- Once everything is set up, you’ll be able to create additional branches from the main branch to [duplicate your development environment in a second](https://neon.tech/blog/how-to-copy-large-postgres-databases-in-seconds), without additional storage costs, as many times as you need.
- Every engineer on your team can have their own dev branch, facilitating parallel development without adding overheads in database management or costs.

🚨 Once you’ve set up your Neon account and your project, **create a database in the main branch, and make a note of the connection string.** You will need this in the next step.

#### Select Your Project -> Connection Details -> Connection String

- On the dashboard, you will see a list of your projects.
- Click on the project for which you want to find the connection string. 
- In the left-hand menu, locate and click on "Connection Details" or "Connect" (this may vary slightly depending on the Neon Console's version).

![Neon Connection Details](/images/Click_Dashboard.png)

- In the Connection Details section, you will see the connection string displayed. Your connection string will be customized with your Neon credentials. Copy the connections string based on the frameworks you are using.
-  View or Generate a Password 
-  If you need a password, look for a button to "Reveal Password" or "Reset Password" in the Connection Details section. Follow the prompts to view or reset it as needed.

### 3. Go back to the VsCode server and open the terminal.

Export the connection string as an environment variable to simplify future connections:

```bash
export DEV_DATABASE_URL="<your-connection-string>" >> ~/.bashrc
```

Then to add to apply your updates run:

```bash
source ~/.bashrc
```




Replace <your-connection-string> with the connection string from your <b> main branch</b> copied from the Neon Console. 

Confirm that the environment variable is set:

```bash
echo $DEV_DATABASE_URL
```

You should see your connection string displayed.

You can now use the connection string to connect to your development database in Neon:
```bash
psql $DEV_DATABASE_URL
```

Or you can use the Neon Console to run queries and explore your database.

Note: This database currently has no table data so running this command below will return no schema/tables: 
```sql
\d
```
![New Neon DB](/images/neon-db-database.png)

However in the Github Actions section, we will automate the process to sync the RDS database with your Neon DB on a nightly scheduled occurrence.


To exit the Neon DB enter:
```sql
\q
```

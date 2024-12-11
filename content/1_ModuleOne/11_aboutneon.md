About Neon: 




Before diving in, there are several things you’ll need to know to build the pg_dump and restore workflow:

RDS connection string
AWS deployment region
A Neon account
A Neon database (deployed to the same AWS region as your RDS database)
While not absolutely necessary, using the same AWS region can help reduce egress charges. Neon does not charge for ingress. 
GitHub repository access to Actions and Secrets
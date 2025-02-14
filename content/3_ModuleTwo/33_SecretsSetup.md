---
title: "Setting up GitHub Secrets"
chapter: true
weight: 33
---

# Setting up GitHub Secrets

In this section, we'll configure the required secrets for our GitHub Actions workflow.

## Gathering your ENV variables:

1. Open a new terminal in **VSCode Server**.  
2. Run these commands to view your connection details in your VSCode Terminal:  

```bash
echo $PROD_DATABASE_URL  # Shows your PROD database URL  
echo $DEV_DATABASE_URL   # Shows the full connection string
```

![Screenshot of Environment Variable Output](/static/images/environment-variables-output.png)  

## 🔐 Adding Repository Secrets

1. Navigate to your GitHub repository and click on "Settings"
2. In the left sidebar, click "Secrets and variables" then "Actions"
3. Click "New repository secret"

![Navigate to Secrets](/static/images/navigate-secrets.png)

4. Add your AWS Role from the previous section:
   - Name: `AWS_ACCOUNT_ROLE`
   - Secret: Add the "GitHubActionsRoleArn" value copied from the OIDC setup cloudformation outputs.

![Add Region Secret](/static/images/add-role-secret.png)

5. Add your RDS connection string:
   - Name: `PROD_DATABASE_URL`
   - Secret: Copy the "PROD_DATABASE_URL" value from  VSCode Terminal output in Step 1 of this section.

![Add Production Secret](/static/images/add-prod-secret2.png)

6. Add your Neon connection string:
   - Name: `DEV_DATABASE_URL`
   - Secret: Your Neon connection string (DEV_DATABASE_URL) value from VSCode Terminal output in Step 1 of this section.

![Add Development Secret](/static/images/add-dev-secret.png)

7. Add your AWS region:
   - Name: `AWS_REGION`
   - Secret: Your AWS region (Needs to be: `us-west-2`)

![Add Region Secret](/static/images/add-region-secret.png)

## ✅ Verification

Confirm all secrets are listed in your repository:
- AWS_ACCOUNT_ROLE
- PROD_DATABASE_URL
- DEV_DATABASE_URL
- AWS_REGION

![Verify Secrets](/static/images/verify-secrets.png)

## 🎯 Next Steps

With our secrets configured, let's set up our GitHub Actions workflow.

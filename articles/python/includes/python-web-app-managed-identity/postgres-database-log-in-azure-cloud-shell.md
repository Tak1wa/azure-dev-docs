---
author: jess-johnson-msft
ms.author: jejohn
ms.topic: include
ms.date: 06/01/2022
---

If you sign into the Cloud Shell with an account other than the one that was set as admin for PostgreSQL, then change accounts with `az login`.

In a Cloud Shell, you can choose between Bash and PowerShell. 

#### [bash](#tab/terminal-bash)

```azurecli
# Sign into Azure as the Azure AD user that was set as Active Directory admin
# az login

# Get an access token for PostgreSQL with the Azure AD user
token=$(az account get-access-token \
    --resource-type oss-rdbms \
    --output tsv \
    --query accessToken)

# View token to confirm
echo $token 

# Sign into the Postgres server
psql "host=<server-name>.postgres.database.azure.com \
    port=5432 \
    dbname=<database-name> \
    user=<aad-user-name>@<server-name> \
    password=$token \
    sslmode=require"
```

#### [PowerShell terminal](#tab/terminal-powershell)

```azurecli
# Sign into Azure as the Azure AD user that was set as Active Directory admin
# az login

# Get an access token for PostgreSQL with the Azure AD user
$token = $(az account get-access-token `
    --resource-type oss-rdbms `
    --output tsv `
    --query accessToken `
    --output tsv)

# View token to confirm
Get-Variable token

# Sign into the Postgres server
psql "host=<server-name>.postgres.database.azure.com `
    port=5432 `
    dbname=<database-name> `
    user=<azure-ad-user-name>@<server-name> `
    password=$token `
    sslmode=require"
```

---

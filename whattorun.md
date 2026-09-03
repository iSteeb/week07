## 3. Create a Service Principal

- Application (Client) ID
- Directory (Tenant) ID
- Client Secret Value
- Azure Subscription ID

read -r SP_APP_ID SP_PASSWORD <<< "$(az ad sp create-for-rbac \
        --name "$SP_NAME" \
--role "AcrPull" \
--scopes "$ACR_ID" \
--query "[appId,password]" \
--output tsv)"

---

---

az acr repository list --name duzkoaacr --output table
az group create \
--name "$RESOURCE_GROUP" \
       --location "$LOCATION"

az acr create \
--resource-group "$RESOURCE_GROUP" \
       --name "$ACR_NAME" \
--sku "$ACR_SKU"

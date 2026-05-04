# ML-inference-Model-Deployment-on-Azure-via-CI-CD-github-actions


Run this command to enable azure container apps in your subscriptions if disabled. 
az provider register -n Microsoft.App --wait

verify by below command
az provider show -n Microsoft.App --query registrationState


Cleanup:

Delete Container Apps:

az containerapp delete \
  --name sentiment-backend \
  --resource-group rg-devops-project \
  --yes

az containerapp delete \
  --name sentiment-frontend \
  --resource-group rg-devops-project \
  --yes
  
Delete containerapp Environment.

az containerapp env delete \
  --name sentiment-env \
  --resource-group rg-devops-project \
  --yes


az group delete --name rg-devops-project

az group list --output table
az containerapp env list -o table
az acr list -o table

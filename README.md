First Set Up a Database: Use a Helm chart to deploy PostgreSQL:

helm repo add bitnami https://charts.bitnami.com/bitnami
helm install jira-postgresql bitnami/postgresql --namespace jira \
  --set global.storageClass=standard \
  --set persistence.size=10Gi \
  --set postgresqlPassword=your_password \
  --set postgresqlDatabase=jiradb \
  --set postgresqlUsername=jirauser
  
Then deploy Jira application and connect it to database.

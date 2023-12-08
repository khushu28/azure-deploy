    pipeline {
    agent any

    environment {
        AZURE_CREDENTIALS = credentials('your-azure-service-principal-id')
        RESOURCE_GROUP_NAME = 'your-resource-group-name'
        AKS_CLUSTER_NAME = 'your-aks-cluster-name'
        LOCATION = 'your-location'
    }

    stages {
        stage('Deploy AKS Cluster') {
            steps {
                script {
                    sh "az login --service-principal -u ${AZURE_CREDENTIALS_USR} -p ${AZURE_CREDENTIALS_PSW} --tenant ${AZURE_CREDENTIALS_TENANT}"
                    sh "az aks create --resource-group ${RESOURCE_GROUP_NAME} --name ${AKS_CLUSTER_NAME} --location ${LOCATION} --node-count 1 --enable-addons monitoring --generate-ssh-keys"
                }
            }
        }

        
    }
}
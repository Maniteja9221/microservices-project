pipeline {
    agent any

    stages {
        stage('Deploy To Kubernetes') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'kubernetes-cred', namespace: 'webapps', serverUrl: 'https://CE58AE562C1CFE192D1C2ABCC9F36966.yl4.eu-north-1.eks.amazonaws.com']]) {
                    sh "kubectl apply -f deployment-service.yml"
                    
                }
            }
        }
        
        stage('verify Deployment') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'kubernetes-cred', namespace: 'webapps', serverUrl: 'https://CE58AE562C1CFE192D1C2ABCC9F36966.yl4.eu-north-1.eks.amazonaws.com']]) {
                    sh "kubectl get svc -n webapps"
                }
            }
        }
    }
}

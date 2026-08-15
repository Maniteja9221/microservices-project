pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t maniteja9221/emailservice:latest .'
            }
        }
        stage('Push image into repo') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'dockerhub-cred') {
                         sh 'docker push maniteja9221/emailservice:latest'
                     }
                }
                }
            }
    }
}

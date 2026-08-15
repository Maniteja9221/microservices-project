pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t Maniteja9221/service:v1 .'
            }
        }
        stage('Push image into repo') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'dockerhub-cred') {
                         sh 'docker push Maniteja9221/service:v1'
                     }
                }
                }
            }
        }
    }
}

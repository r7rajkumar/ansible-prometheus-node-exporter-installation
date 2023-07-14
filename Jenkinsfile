pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Deploy Prometheus Node Exporter') {
            steps {
                withCredentials([sshUserPrivateKey(credentialsId: 'bd18aa96-90f1-4d29-93de-fd9910fc77b4', keyFileVariable: 'SSH_KEY')]) {
                    sh 'ansible-playbook -i inventory playbook.yml --private-key=$SSH_KEY'
                }
            }
        }
    }
    
    post {
        success {
            echo 'Pipeline succeeded!'
        }
        
        failure {
            echo 'Pipeline failed!'
        }
    }
}



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
                sh 'ansible-playbook -i inventory playbook.yml'
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

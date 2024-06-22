pipeline {
    agent any

    stages {
        stage('Deploy App on k8s') {
            steps {
                withCredentials([file(credentialsId: 'kubeconfig', variable: 'KUBECONFIG')]) {
                    sh 'kubectl --kubeconfig=$KUBECONFIG apply -f deployment.yaml'
                    sh 'kubectl --kubeconfig=$KUBECONFIG apply -f service.yaml'
                }
            }
        }
    }
}


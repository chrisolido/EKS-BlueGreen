pipeline {
    agent any
    stages {
        stage('Build and Deploy Blue') {
            steps {
                sh 'kubectl apply -f blue.yaml --namespace bluegreen'
                sh 'kubectl apply -f blueservice.yaml --namespace bluegreen'
            }
        }
        stage('Deploy Green'){
            steps {
                sh 'kubectl apply -f green.yaml --namespace bluegreen'
            }
        }
        stage('Switch to green') {
            steps {
                sh 'kubectl apply -f greenservice.yaml --namespace bluegreen'
            }
        }
    }
}

pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                bat 'mvn clean package cobertura:cobertura -Pmetrics'
            }
        }
    }
}

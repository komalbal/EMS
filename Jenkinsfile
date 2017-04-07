pipeline {
    agent any
    stages {
        stage('Build, Test, Package') {
            steps {
                bat 'mvn clean package'
            }
        }
        stage('Code Coverage') {
            steps {
                bat 'mvn cobertura:cobertura -Pmetrics'
            }
        }
        stage('Static Code Analysis') {
            steps {
                bat 'sonar-scanner'
            }
        }
    }
    post {
        always {
            junit '**/target/surefire-reports/*.xml'
            publishHTML(target: [
                allowMissing: false, 
                alwaysLinkToLastBuild: false, 
                keepAll: false, 
                reportDir: 'target/site/cobertura', 
                reportFiles: 'index.html', 
                reportName: 'HTML Report'])
        }
    }
}

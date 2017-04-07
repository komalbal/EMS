pipeline {
    agent any
    stages {
        stage('Build, Test, Package') {
            steps {
                bat 'mvn clean package'
            }
        }
        stage('Code Coverage')
            steps {
                bat 'mvn cobertura:cobertura -Pmetrics'
            }
        }
        stage('Static Code Analysis')
            steps {
                bat 'sonar-scanner'
            }
        }
    }
}

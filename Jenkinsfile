pipeline {
    agent any
    options {
        buildDiscarder(logRotator(numToKeepStr: '5'))
    }
    stages {
        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('test') {
                    sh 'sonar-scanner -Dsonar.projectKey=demosonar -Dsonar.sources=. -Dsonar.host.url=http://localhost:9000 -Dsonar.login="admin" -Dsonar.password="admin"'
                }
            }
        }
    }
}
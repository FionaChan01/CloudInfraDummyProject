pipeline {
    agent any
    options {
        buildDiscarder(logRotator(numToKeepStr: '5'))
    }
        // stage('Checkout') {
        //     steps {
        //         git 'https://github.com/FionaChan01/CloudInfraDummyProject.git'
        //     }
        // }

    stage('SonarQube Analysis') {
        steps {
            withSonarQubeEnv(installationName: 'test' {
                sh 'sonar-scanner -Dsonar.projectKey=demosonar -Dsonar.sources=. -Dsonar.host.url=http://localhost:9000 -Dsonar.login="admin" -Dsonar.password="admin"'
            }
        }
    }
}

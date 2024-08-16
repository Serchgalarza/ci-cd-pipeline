pipeline {
    agent any
    environment {
        SONARQUBE_SCANNER_HOME = tool name: 'SonarQube Scanner', type: 'SonarQubeScanner'
    }
    stages {
        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('SonarQube') { // 'SonarQube' es el nombre del servidor configurado en Jenkins
                    sh "${SONARQUBE_SCANNER_HOME}/bin/sonar-scanner"
                }
            }
        }
    }
}


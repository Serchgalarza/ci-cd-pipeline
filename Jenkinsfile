pipeline {
    agent any
    environment {
        SONARQUBE = 'SonarQube'  // Nombre del servidor SonarQube configurado en Jenkins
        SONARQUBE_SCANNER_HOME = tool name: 'SonarQube Scanner', type: 'SonarQubeScanner'
    }
    stages {
        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('SonarQube') {  // Usa el nombre de la configuración de SonarQube en Jenkins
                    sh """
                        ${SONARQUBE_SCANNER_HOME}/bin/sonar-scanner \
                            -Dsonar.projectKey=ci-cd-pipeline \
                            -Dsonar.sources=src \
                            -Dsonar.host.url=http://localhost:9000
                    """
                }
            }
        }
        // Otros stages
    }
    post {
        always {
            // Puedes añadir más acciones aquí, como la publicación de resultados de análisis
        }
    }
}




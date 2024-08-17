
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
                            -Dsonar.host.url=http://34.82.231.134:9000 \
                            -Dsonar.login=sqp_62967d39d7beed11b3f737be37f979e82dc69331
                    """
                }
            }
        }
        // Otros stages
    }
    post {
        always {
            echo "El análisis fue correcto"
        }
    }
}







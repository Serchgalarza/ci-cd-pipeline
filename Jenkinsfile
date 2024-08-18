pipeline {
    stage('SonarQube Analysis') {
    steps {
        script {
            def scannerHome = tool 'SonarQubeScanner'
            withSonarQubeEnv('SonarQube') {
                sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=ci-cd-pipeline -Dsonar.host.url=http://34.82.231.134:9000 -Dsonar.login=sqp_62967d39d7beed11b3f737be37f979e82dc69331"
                }
            }
        }
    }

}








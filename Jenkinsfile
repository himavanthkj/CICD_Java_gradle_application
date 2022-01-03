pipeline{
    agent none 
    environment{
        VERSION = "${env.BUILD_ID}"
    }
    stages{
        stage("sonar quality check"){
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'token') {
                            sh 'chmod +x gradlew'
                            sh './gradlew sonarqube'
                        }
                    }

                }  
            }
        }
}

pipeline{
    agent any 
    environment{
        VERSION = "${env.BUILD_ID}"
    }
    stages{
        stage("sonar quality check"){
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonar-token3') {
                            sh 'chmod +x gradlew'
                            sh './gradlew sonarqube'
                        }
                    }

                }  
            }
        }
}

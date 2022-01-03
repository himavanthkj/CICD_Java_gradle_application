pipeline{
    agent none 
    environment{
        VERSION = "${env.BUILD_ID}"
    }
    stages{
        stage("sonar quality check"){
            agent {
                docker {
                    image 'openjdk:11'
                }
            }
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

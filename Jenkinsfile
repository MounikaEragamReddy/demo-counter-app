pipeline{
    agent any
    stages{
        stage("Git Checkout"){
            steps{
                git branch: 'main', url: 'https://github.com/MounikaEragamReddy/demo-counter-app.git'
            }
        }
        stage("MVN UnitTest"){
            steps{
                sh 'mvn test'
            }
        }
        stage("Integration testing"){
            steps{
                sh 'mvn verify -DskipUnitTests'
            }
        }
        stage("maven Build"){
            steps{
                sh 'mvn clean install'
            }
        }
        stage("static code analysis"){
            steps{
                script{
                withSonarQubeEnv(credentialsId:'sonar-api'){
                sh 'mvn clean package sonar:sonar'
                }
               }
            }
        }
    }
}

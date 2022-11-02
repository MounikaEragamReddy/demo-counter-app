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
    }
}

pipeline{
    agent { label 'mgk-agent'}
    tools {
        maven 'maven3'
        jdk 'Java17'

    }
    stages{
        stage('Cleanup workspace'){
            steps{
                cleanWs()
            }
        }
        stage('Checkout from guthub'){
            steps{
                git branch: 'main', credentialsId: 'github', url:'https://github.com/mgk1999/register-app.git'
            }
        }
        stage('Build'){
            steps{
                sh 'mvn clean package'
            }
        }
        stage('Test'){
            steps{
                sh 'mvn test'
            }
        }
        stage("ok"){
            steps{
                echo "fini"
            }
        }

    }
}

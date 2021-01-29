pipeline {
    tools {
        jdk 'myjava'
        maven 'mymaven'
    }
    agent any

    stages {
        stage('Compile'){
            steps{
                sh 'mvn compile'
            }
        }  
        
        stage('Test'){
            steps{
                sh 'mvn test'
            }
            post{
                always {
                    junit 'gameoflife-web/target/surefire-reports/*.xml'
                }
            }
        }  
        
        stage('Package'){
            steps{
                git 'https://github.com/devops-trainer/game-of-life.git'
                sh 'mvn package'
            }
        }  
        
    }
}
